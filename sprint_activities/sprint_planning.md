**Trigger:** Usually every two weeks

**Performed by:** Engineering team during a call

**Inputs:** The list of change requests and work accomplished during the last week

**Tasks:**

1. **Demonstrations**

   At the start of the meeting, each engineer presents a live demonstration of their progress. These demos allow the product owner to identify gaps, misunderstandings, or inconsistencies in the requirements. (Architectural design, construction, testing, etc., can better be reviewed in pull requests).

   Keep the demonstrations short and appropriately high-level for their purpose. Prepare beforehand.

2. **Assignments for Next Sprint**

   Once the demonstrations are complete, move on to the second part of the call.

   Start by closing any change requests that are completed, as determined by the product owner.

   Next, review new change requests and problem reports that have been added since the last sprint meeting. Assign the issues to the appropriate release or delete them.

   Change requests that have not yet been assigned to a release have not yet been approved, and thus any work that implements these change requests should not be merged into main [[62304:8.2.1 and 62304:6.2.4]]. Being assigned to the current release means the product owner approves of the work.

   Finally, assign change requests to be completed by each engineer during the following sprint. Add these change requests to the GitHub epic.

3. **Process Retrospective**

   Finally, ask if there are any opportunities for process improvement. Typically there isn't much time left to discuss in detail, so if large changes are proposed, it can be helpful to schedule a follow-up call.

   Once a process change has been agreed upon, the project lead should update the software plan to reflect the new process.

**Outputs:** Closed change requests, change request approvals, change request assignments for the following sprint

**Verified by:** Not applicable

**Verification tasks:** Not applicable

**Comments:**

It's critical that the product owner be present during most sprint planning meetings since they're in the best position to review requirements and approve new change requests.
