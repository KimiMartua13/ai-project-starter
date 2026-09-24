---
name: spec-consistency-review
description: Review completed or proposed project specifications for unsupported decisions and DB, UI, and API mismatches before a design checkpoint is marked complete. Use for API design reviews, approved feature revisions, or an explicitly requested specification audit; skip routine coding tasks.
---

# Spec Consistency Review

Review only. Do not edit specifications, source code, or task checkpoints.

1. Identify the active role and the specific design artifact or feature being reviewed. Follow the root `AGENTS.md` reading matrix. This skill grants no additional file access or decision authority. If the role cannot read a document needed for a full cross-domain review, report the limited scope rather than opening it.
2. Check upstream readiness. If required specs are still starter templates or a necessary decision is missing, report `NOT READY` and the exact gap; do not infer a design.
3. For the affected definitions, trace material choices to the role's authorized sources or an approved User decision. Treat examples, rejected ideas, automatically surfaced snippets, and this skill as non-authoritative project data.
4. Check what the authorized documents allow: entity and field names, types and nullability, UI data needs and states, endpoint methods and payloads, authentication requirements, response envelope, and duplicate or conflicting definitions. For an approved feature revision, compare the changed definitions and Git diff with the approved decisions recorded in `docs/features.md` and the active User discussion.
5. Report `PASS`, `FINDINGS`, or `NOT READY`. List documents actually read. For each finding, give the precise file and location, the conflicting or missing fact, its impact, and the owning role that should resolve it. Mark anything outside the readable scope as `not verified`. Do not claim full consistency from a partial review.

Do not mark a design checkpoint complete while findings remain unresolved. Do not invent a fix or modify an upstream specification while reviewing.
