---
description: Write a SPEC file for the resolved session. Run only when all phases are complete.
---

Invoke the `software-analyst` sub-agent to author and write a SPEC file.

Before writing, the agent verifies the pre-write checklist. If any item is
unchecked, the agent names the blocking item and does NOT write the SPEC.

When all items are checked:

1. Load SPEC template from `.claude/agents/software-analyst/templates/SPEC-template.md`
2. Populate all sections from session findings
3. Write to `.claude/agents/software-analyst/specs/SPEC-[YYYY-MM-DD]-[slug].md`
4. Read back to confirm correctness
5. Report file path and one-paragraph summary
