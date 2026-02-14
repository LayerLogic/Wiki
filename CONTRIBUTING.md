# Contributing to LayerLogic Documentation

Thank you for contributing to LayerLogic's SDLC documentation! This guide will help you make effective contributions.

---

## Quick Start

1. **Create a change request** — Open a GitHub issue describing the documentation change
2. **Create a branch** — Name it `<issue-number>-short-description`
3. **Make your changes** — Follow the standards below
4. **Create a pull request** — Use the PR template and reference the issue
5. **Get reviewed & merge** — Assign a reviewer, address feedback, and merge

---

## Document Structure

### Activity Document Format

All activity documents **must** follow this structure:

```markdown
## [Layer] — [Activity Name]

> One-line description of the activity.

---

**Trigger:** [When this activity is initiated]

**Performed by:** [Role(s) responsible]

**Inputs:** [What information/artefacts are needed]

---

### Tasks

#### 1. [Task Name]

[Task description]

#### 2. [Task Name]

[Task description]

---

**Outputs:** [What this activity produces]

**Verified by:** [Who verifies the outputs]

### Verification Tasks

1. **[Task Name]** — [Description]
```

### Naming Conventions

| Type                | Convention           | Example                     |
| ------------------- | -------------------- | --------------------------- |
| **Files**           | `snake_case.md`      | `creating_pull_requests.md` |
| **Directories**     | `snake_case`         | `issue_activities`          |
| **Headings**        | Title Case with `##` | `## Issue — Writing Tests`  |
| **Regulatory refs** | Double brackets      | `[[62304:5.5.1]]`           |

### Cross-References

Always use **relative markdown links** when referencing other documents:

```markdown
<!-- Good -->

See the [Testing Plan](../plans/testing_plan.md)

<!-- Bad — don't use absolute paths or anchors to non-existent sections -->

See the [Testing Plan](#testing-plan)
```

---

## Writing Style

- **Be concise** — Use short sentences and bullet points
- **Be actionable** — Write tasks as instructions, not descriptions
- **Use checklists** — `- [ ]` for verification and task items
- **Use tables** — For structured data that would otherwise be a wall of text
- **Use code blocks** — For commands, examples, and templates
- **Active voice** — "The engineer reviews..." not "The review is done by..."

---

## Regulatory References

When referencing IEC 62304 or FDA guidance:

- Use the format `[[62304:X.X.X]]` inline
- Multiple clauses: `[[62304:5.1.1.a, 62304:5.1.1.b]]`
- FDA references: `[[FDA-SW:section-name]]`
- Place references at the end of the relevant sentence or paragraph

---

## Review Process

Documentation changes follow the same review process as code:

1. Changes are reviewed via GitHub pull request
2. The reviewer checks for accuracy, completeness, and formatting
3. Changes must be approved before merging
4. All commits must reference the change request number

---

_If you have questions about contributing, reach out to the project lead._
