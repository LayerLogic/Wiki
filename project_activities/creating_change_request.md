## Project — Creating Change Requests

> How to record and manage chunks of development work as GitHub issues.

---

**Trigger:** Need to record a chunk of development work

**Performed by:** Anyone on the project

**Inputs:** User needs, requirements, or identified improvements

---

### Tasks

#### 1. Write Change Request

Create a GitHub issue using the appropriate issue template:

- **[Bug Report](../.github/ISSUE_TEMPLATE/bug_report.yaml)** — for defects and unexpected behaviour
- **[Feature Request](../.github/ISSUE_TEMPLATE/feature_request.yaml)** — for new functionality
- **[Change Request](../.github/ISSUE_TEMPLATE/change_request.yaml)** — for modifications to existing functionality

**Granularity guidelines:**

| Timeline             | Granularity                                                      |
| -------------------- | ---------------------------------------------------------------- |
| **Upcoming sprints** | More granular — each issue should be completable within 1 sprint |
| **Future releases**  | Less granular — issues can be broader and will be refined later  |

Since change requests may be split up later and detailed requirements are added in an agile fashion, this activity allows **minimal detail** to be added to the change request. Sometimes even a title is sufficient.

#### 2. Assign to Release (if applicable)

- **Unless you're the project lead**, don't assign the issue to a release milestone. That will be handled during [Sprint Planning](../sprint_activities/sprint_planning.md).
- If, however, you know the issue won't be tackled in any current release, feel free to add it to the **icebox** milestone.

#### 3. Add Labels

Apply the appropriate label(s):

| Label           | When to Use                       |
| --------------- | --------------------------------- |
| `bug`           | Problem reports and defects       |
| `feature`       | New feature requests              |
| `enhancement`   | Improvements to existing features |
| `documentation` | Documentation-only changes        |

---

**Outputs:** Change request (GitHub issue)

**Verified by:** Not applicable

**Verification tasks:** Not applicable
