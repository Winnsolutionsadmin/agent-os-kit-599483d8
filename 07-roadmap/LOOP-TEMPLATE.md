# Wiggum loop template (applies to every workstream without its own loop.md)

W0, W1, and W3 carry bespoke loop.md files. W4-W10 run THIS template with their own tasks.md.

## Loop prompt (parameterize <KEY>, <SLUG>)
You are the <KEY> loop for agent-os-foundation, branch `ws/<KEY>-<SLUG>` (OmnaraBranch worktree, never bare git worktree add). Read CLAUDE.md corrections 1-7 and decision 0003 first; they override everything. Open 07-roadmap/<KEY>-<SLUG>/tasks.md, take the top unblocked task, produce the REAL artifact (doc, spec, schema, analysis; never a summary of intent), commit with a `<key>:` prefix, update the task row, push, repeat. Stop at any row whose Gate column names a human. Mirror state changes to ClickUp list 901819360023.

## Universal done criteria
- Backlog dry or every remaining row gated/blocked-external.
- Every number lineage-tagged (MEASURED / SURVEY / VENDOR / [unverified]).
- No em dashes. Product UNNAMED. No Upexi or Mima references. Recurro only as Carter's framework.

## Universal human gates
- Money, irreversible, external (anything leaving the repo toward Nick, Carter, Alan, counsel, or any third party): founder.
- Founder-level questions (equity, positioning, the ask, achievement definition): never decided by a loop.

## Liveness
At least one commit per iteration; a loop that goes silent is treated as broken and gets pulsed.
