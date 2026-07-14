# API Specification: Agent OS Foundation

**Version:** 0.1 (pre-alpha)  
**Last updated:** 2026-07-08  
**Status:** Framework; detailed endpoints to be authored per workstream

---

## I. Overview

The API is the surface layer between agents, clients, and the product backend. It defines:
- Authentication + authorization patterns
- Core resource models
- Agent integration lifecycle
- Client embed + OAuth flow

### Design Principles
1. **Agent-first:** SDK and examples for agent developers
2. **Multi-tenant:** Every request carries org_id context
3. **Audit-ready:** All actions logged with user/agent/timestamp
4. **Rate-limited:** Fair token allocation per tenant
5. **Versioned:** API versioning for backward compatibility

### Technology Choice
- **Framework:** FastAPI (Python 3.11+)
- **ASGI:** Uvicorn (production-grade async)
- **Database:** Postgres (SQLAlchemy ORM)
- **Auth:** OAuth 2.0 + JWT tokens
- **Monitoring:** OpenTelemetry + structured JSON logs

---

## II. Authentication & Authorization

### OAuth 2.0 Flow (Clients)
```
1. Client redirects user to /auth/authorize
2. User logs in (via third-party or internal auth)
3. User approves scopes
4. Redirect to callback with authorization code
5. Client exchanges code for access token + refresh token
6. Client includes access token in Authorization header
```

### Service Accounts (Agents)
```
1. Agent registers via /agents/register (admin approval)
2. Returns API key (format: agent_<org_id>_<random>)
3. Agent includes key in Authorization header: "Bearer agent_xyz"
4. API validates key + org membership before executing
```

### JWT Token Structure
```json
{
  "sub": "user_or_agent_id",
  "org_id": "org_123",
  "roles": ["admin", "agent"],
  "scopes": ["read:okr", "write:tasks"],
  "iat": 1720569600,
  "exp": 1720656000
}
```

### Authorization Model
- **RBAC (Role):** user, agent, admin, guest (org-level)
- **ABAC (Context):** org_id must match token org_id; per-resource checks via RLS
- **Scopes:** read:okr, write:tasks, read:decisions, write:gamification, etc.

---

## III. Core Resource Models

### Org (Multi-tenant Root)
```json
{
  "id": "org_123",
  "name": "Acme Corp",
  "status": "active",
  "tier": "pilot",
  "created_at": "2026-07-01T00:00:00Z",
  "settings": {
    "timezone": "America/New_York",
    "locale": "en-US",
    "gamification_enabled": true
  }
}
```

### User
```json
{
  "id": "user_456",
  "org_id": "org_123",
  "email": "alice@acme.com",
  "name": "Alice Chen",
  "role": "admin",
  "created_at": "2026-07-01T00:00:00Z"
}
```

### OKR
```json
{
  "id": "okr_789",
  "org_id": "org_123",
  "type": "north_star",
  "title": "Compress time between thought and output",
  "weight": 1.0,
  "parent_id": null,
  "children": ["okr_790", "okr_791"],
  "status": "active",
  "created_by": "user_456",
  "created_at": "2026-07-01T00:00:00Z"
}
```

### Task
```json
{
  "id": "task_101",
  "org_id": "org_123",
  "title": "Review Q3 budget",
  "status": "open",
  "okr_id": "okr_789",
  "assigned_to": "user_456",
  "priority": "high",
  "due_date": "2026-07-15T00:00:00Z",
  "created_by": "agent_xyz",
  "created_at": "2026-07-08T12:00:00Z"
}
```

### Decision
```json
{
  "id": "decision_202",
  "org_id": "org_123",
  "type": "approval",
  "title": "Approve OKR rewrite",
  "question": "Does this align with our North Star?",
  "options": ["yes", "no", "discuss"],
  "created_by": "agent_xyz",
  "approver_id": "user_456",
  "status": "pending",
  "context": {
    "okr_id": "okr_789",
    "agent_session_id": "session_001"
  },
  "created_at": "2026-07-08T12:00:00Z"
}
```

### Achievement (Gamification)
```json
{
  "id": "achievement_303",
  "org_id": "org_123",
  "user_id": "user_456",
  "event_type": "task_completed",
  "points": 42,
  "tier": "rare",
  "streak": 23,
  "created_at": "2026-07-08T12:05:00Z"
}
```

---

## IV. Core Endpoints

### Authentication
- `POST /auth/authorize` - Initiate OAuth flow
- `POST /auth/callback` - Exchange code for token
- `POST /auth/token/refresh` - Refresh expired token
- `POST /agents/register` - Agent registration (admin approval)

### Orgs (Multi-tenant Management)
- `GET /orgs/{org_id}` - Fetch org details
- `PATCH /orgs/{org_id}` - Update org settings
- `GET /orgs/{org_id}/settings` - Fetch settings only

### Users
- `GET /orgs/{org_id}/users` - List org users
- `GET /orgs/{org_id}/users/{user_id}` - Fetch user
- `POST /orgs/{org_id}/users` - Create user (admin only)
- `PATCH /orgs/{org_id}/users/{user_id}` - Update user

### OKRs
- `GET /orgs/{org_id}/okrs` - List OKRs (with filtering/search)
- `GET /orgs/{org_id}/okrs/{okr_id}` - Fetch OKR
- `POST /orgs/{org_id}/okrs` - Create OKR
- `PATCH /orgs/{org_id}/okrs/{okr_id}` - Update OKR
- `POST /orgs/{org_id}/okrs/{okr_id}/score` - Trigger scoring run
- `GET /orgs/{org_id}/okrs/{okr_id}/alignment` - Fetch alignment report

### Tasks
- `GET /orgs/{org_id}/tasks` - List tasks (with filtering/search)
- `GET /orgs/{org_id}/tasks/{task_id}` - Fetch task
- `POST /orgs/{org_id}/tasks` - Create task
- `PATCH /orgs/{org_id}/tasks/{task_id}` - Update task
- `POST /orgs/{org_id}/tasks/{task_id}/close` - Mark task done

### Decisions
- `GET /orgs/{org_id}/decisions` - List pending decisions
- `GET /orgs/{org_id}/decisions/{decision_id}` - Fetch decision
- `POST /orgs/{org_id}/decisions` - Create decision
- `POST /orgs/{org_id}/decisions/{decision_id}/respond` - Submit response
- `GET /orgs/{org_id}/decisions/{decision_id}/history` - Decision audit trail

### Achievements (Gamification)
- `GET /orgs/{org_id}/users/{user_id}/achievements` - List achievements
- `GET /orgs/{org_id}/leaderboard` - Org leaderboard (ranked)
- `GET /orgs/{org_id}/streaks` - Current streaks snapshot

### Sessions (Agent Integration)
- `POST /agents/sessions` - Create agent session (with org_id context)
- `GET /agents/sessions/{session_id}` - Fetch session state
- `POST /agents/sessions/{session_id}/events` - Emit event (task created, etc.)
- `POST /agents/sessions/{session_id}/decisions/request` - Request human decision
- `POST /agents/sessions/{session_id}/decisions/{decision_id}/callback` - Webhook callback on decision

### Audit & Logging
- `GET /orgs/{org_id}/audit-log` - Fetch audit trail (admin only)
- `GET /orgs/{org_id}/audit-log/{event_id}` - Fetch single event

---

## V. Agent Integration Patterns

### Agent Session Lifecycle
```
1. Agent calls POST /agents/sessions (includes org_id, user_context)
2. Returns session_id + context (org settings, user role, OKR tree, etc.)
3. Agent executes work; emits events via POST /agents/sessions/{session_id}/events
4. When decision needed: POST .../decisions/request
5. Agent polls or receives webhook on decision callback
6. Agent completes work; session auto-closes after 24h
```

### Example: Task Creation from Agent
```
POST /agents/sessions/session_001/events
{
  "type": "task.created",
  "data": {
    "title": "Review budget for Q3",
    "okr_id": "okr_789",
    "assigned_to": "user_456",
    "priority": "high"
  }
}
```

### Example: Decision Request
```
POST /agents/sessions/session_001/decisions/request
{
  "type": "approval",
  "title": "Approve task assignment",
  "question": "Does alice have bandwidth for this?",
  "context": {
    "task_id": "task_101"
  },
  "approver_id": "user_456",
  "timeout_seconds": 3600
}
```

---

## VI. Rate Limiting

### Quotas
- **Free tier:** 1,000 requests/day per org
- **Pilot tier:** 10,000 requests/day + 100 agent sessions/day
- **Enterprise tier:** Custom (>100k requests/day)

### Rate Limit Headers
```
X-RateLimit-Limit: 10000
X-RateLimit-Remaining: 9950
X-RateLimit-Reset: 1720656000
```

### Backoff Strategy
- Return 429 (Too Many Requests) when quota exceeded
- Include `Retry-After: 60` header
- Client should exponential backoff (1s, 2s, 4s, 8s...)

---

## VII. Error Responses

### Standard Error Format
```json
{
  "error": "invalid_request",
  "error_description": "Missing required parameter: okr_id",
  "request_id": "req_abc123",
  "timestamp": "2026-07-08T12:00:00Z"
}
```

### Common Status Codes
- `400` - Bad request (validation error)
- `401` - Unauthorized (invalid/missing token)
- `403` - Forbidden (insufficient permissions)
- `404` - Not found
- `409` - Conflict (stale version, duplicate resource)
- `429` - Rate limit exceeded
- `500` - Server error

---

## VIII. Versioning

### Strategy
- **URL-based:** `/api/v1/...`, `/api/v2/...`
- **Backward compatibility:** Previous version supported for 6 months
- **Breaking changes:** New major version only

### Deprecation Notice
```
Deprecation: 2026-08-08
Sunset: 2027-01-08
Header: Deprecation: true
Link: </api/v2/...>; rel="successor-version"
```

---

## IX. Webhooks (Future)

Plan for agent -> product callbacks when decisions complete:
```
POST https://customer-agent-endpoint.com/callback
{
  "webhook_id": "wh_xyz",
  "event": "decision.completed",
  "data": {
    "decision_id": "decision_202",
    "response": "yes",
    "context": { "okr_id": "okr_789" }
  },
  "signature": "sha256=..." (HMAC validation)
}
```

---

## X. SDKs

### Python SDK (Claude agent ecosystem)
```python
from agent_os import Client

client = Client(api_key="agent_org_123_abc", org_id="org_123")
session = client.create_session()
session.create_task(title="...", okr_id="...")
decision = session.request_decision(...)
```

### JavaScript SDK (Client embed)
```javascript
import { AgentOS } from "@agent-os/sdk";

const client = new AgentOS({ clientId: "..." });
client.authenticate().then(() => {
  client.getOKRs().then(okrs => { /* ... */ });
});
```

---

**Next:** Detailed endpoint specs per workstream (W3/W5/W4). This is the framework.

