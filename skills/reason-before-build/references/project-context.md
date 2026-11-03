# Repository project context

Use a compact, repository-local context note to preserve only facts that materially affect future application decisions. The `assets/project-context.template.md` file is an optional starting point, not a required new file.

## Discover before creating

1. Look for current repository guidance and maintained product, architecture, role, data, and design documentation.
2. Reuse the best existing source of truth. Do not create a competing summary or copy large sections of existing docs.
3. If no suitable source exists and durable context would prevent meaningful rediscovery, create one small file in the repository's established documentation location. If there is no convention, use `docs/PROJECT-CONTEXT.md`. Start from [the optional template](../assets/project-context.template.md) and omit sections that do not apply.
4. Keep confirmed facts separate from assumptions and open questions. Link to authoritative repo files instead of copying their details.

Capture the purpose and key workflows, roles and hierarchy/access scope, important architecture and data contracts, existing features and reusable components, confirmed decisions/constraints, and authoritative file pointers. Record unknowns as unknowns. A short pointer in existing repository guidance is useful when it improves discovery; preserve all existing instructions and avoid duplicating the workflow there.

Before trusting an old summary, verify the relevant facts against current code, schemas, and maintained documentation. Resolve conflicts according to the authority for that fact: runtime behavior comes from implementation evidence; intended policy comes from confirmed product rules. Surface unresolved conflicts instead of guessing.

## Update only after material changes

Update the repository context automatically when implementation or a confirmed decision changes a durable fact that would alter future work, such as:

- product purpose, user roles, responsibilities, hierarchy, or access boundaries;
- a shared KPI definition, source of truth, or cross-level aggregation rule;
- a stable workflow or architectural boundary;
- an accepted product decision or constraint that future tasks must preserve.

Do not record routine code changes, temporary mock values, unconfirmed proposals as decisions, or details already maintained in a more authoritative file. Add the smallest useful note, preserve existing decisions, and remove stale entries when their source of truth changes. Keep the file short enough to scan quickly; link out for detail. Do not append a task-by-task activity log or refresh timestamps when nothing material changed.

## Safety and scope

Write only inside the current repository and only when the repository is writable and the task permits edits. Honor read-only, audit-only, or planning-only requests: report a needed context correction instead of writing it in those modes. Do not modify agent-wide settings, unrelated repositories, or external systems. Follow repository instructions and existing ownership conventions. If no material context changed, leave the context file alone.

Keep secrets, credentials, personal records, and sensitive internal content out of shareable context. Automatic context maintenance does not authorize an automatic commit or push. Review the documentation diff for correctness and appropriate disclosure before including it in a user-authorized Git operation.
