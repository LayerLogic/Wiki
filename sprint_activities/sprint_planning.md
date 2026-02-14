## Sprint — Sprint Planning

> The recurring ceremony for demonstrations, assignments, and process improvement.

---

**Trigger:** Usually every two weeks (at the start of each sprint)

**Performed by:** Engineering team during a call (product owner **must** attend)

**Inputs:** The list of change requests and work accomplished during the last sprint

---

### Tasks

#### 1. Demonstrations (≈15 minutes)

Each engineer presents a **live demonstration** of their progress from the previous sprint.

**Guidelines:**

- [ ] Keep demonstrations short and appropriately high-level
- [ ] Prepare beforehand — have the demo environment ready
- [ ] Focus on user-visible progress and key decisions
- [ ] The product owner uses demos to identify gaps, misunderstandings, or inconsistencies in requirements
- [ ] Architectural design, construction, and testing are better reviewed in pull requests

#### 2. Assignments for Next Sprint (≈20 minutes)

**Close completed work:**

- [ ] Close change requests that are completed, as determined by the product owner

> **Important:** Change requests that have not been assigned to a release have not been approved. Work implementing unapproved change requests should **not** be merged into `main` [[62304:8.2.1, 62304:6.2.4]]. Being assigned to the current release means the product owner approves of the work.

**Review new items:**

- [ ] Review new change requests and problem reports added since the last sprint
- [ ] Assign issues to the appropriate release milestone or move to icebox
- [ ] Delete or mark as `obsolete` any issues that are no longer relevant

**Assign work:**

- [ ] Assign change requests to each engineer for the upcoming sprint
- [ ] Ensure assignments are realistic given the sprint duration
- [ ] Add assigned change requests to the current sprint's GitHub milestone or project board

#### 3. Process Retrospective (≈10 minutes)

- [ ] **Ask:** Are there any opportunities for process improvement?
- [ ] If large changes are proposed, schedule a follow-up call to discuss in detail
- [ ] Once a process change is agreed upon, the project lead updates the software plan to reflect the new process

**Suggested retrospective format:**

| Category           | Question                    |
| ------------------ | --------------------------- |
| 🟢 **Keep doing**  | What went well this sprint? |
| 🟡 **Start doing** | What should we try?         |
| 🔴 **Stop doing**  | What's not working?         |

---

**Outputs:** Closed change requests, change request approvals, change request assignments for the following sprint

**Verified by:** Not applicable

**Verification tasks:** Not applicable

---

**Comments:**

It's critical that the product owner be present during most sprint planning meetings since they're in the best position to review requirements and approve new change requests.
