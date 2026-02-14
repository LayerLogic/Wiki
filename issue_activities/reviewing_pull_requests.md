## Issue — Reviewing Pull Requests

> How to perform a thorough and constructive code review.

---

**Trigger:** Assignment to review a pull request

**Performed by:** The designated reviewer

**Inputs:** The content of the pull request (code changes, PR description, linked change request)

---

### Tasks

#### 1. Identify Activities Performed

Using the pull request description and the content of the changes, determine which SDLC activities were performed (fully or partially):

- [ ] Requirements Analysis
- [ ] Design Specifications
- [ ] Risk Analysis
- [ ] Implementation / Construction
- [ ] Writing Tests
- [ ] Adding Dependencies

If it's unclear which activities were performed, ask the PR author for clarification.

#### 2. Determine Appropriateness

Before beginning the review, confirm:

- [ ] **You are the right reviewer.** Some activities require specific roles (e.g., project lead) to perform verification. If the activity specifies someone else, request that they perform the review.
- [ ] **You have adequate context.** If the code involves safety-critical modules and you aren't familiar with the codebase or don't have enough time for a thorough review, request that someone more qualified perform the review.

#### 3. Perform Verification Activities

Step through the verification tasks for each performed activity [[62304:5.5.3]]. Record the tasks you performed in your review response using a markdown checklist:

```markdown
**Verification Checklist:**

- [x] Documents and implements software requirements
- [x] Updates design specifications
- [x] Risk analysis performed / not applicable
- [ ] Code construction follows project standards
- [ ] Unit, integration, or manual tests are updated
- [ ] New sequences of events have been recorded
- [ ] Dependencies evaluation completed (if applicable)
```

> **Tip:** Most git hosting platforms support saved/template replies. Set up a saved reply with this checklist template for efficiency.

It's okay to skip common, low-risk verification tasks (e.g., "Git Commit Messages Include Change Request Numbers" for every commit).

#### 4. Write Feedback

**Best practices for code review feedback:**

- ✅ **Ask questions before making suggestions** — understand intent before prescribing changes
- ✅ **Compliment good work** — positive reinforcement improves team morale
- ✅ **Be specific** — reference line numbers and explain _why_ a change is needed
- ✅ **Distinguish severity** — use prefixes like `nit:`, `suggestion:`, or `blocking:` to clarify importance
- ✅ **Suggest documentation** — if a comment would be useful long-term, suggest adding it to the codebase

**When there's nothing to say:**

It's fine to approve without comments. But distinguish between:

- "I did a thorough review and found nothing to comment on" → state this explicitly
- "I didn't have time for an in-depth review" → state this and consider requesting an additional reviewer

**When you disagree:**

If you're surprised by a change, ask the author _why_ they did it that way. Sometimes there's a good reason you hadn't considered.

#### 5. Sign Off

- [ ] If satisfied with the changes, **approve** the pull request [[62304:8.2.4.c]]
- [ ] If changes are required, mark the PR as "Changes Requested" and clearly indicate what must be addressed
- [ ] If suggested changes are **low-risk**, it's okay to approve before the author implements them (avoid unnecessary round-trips)

**Handling incomplete outputs:**

Since we use an agile methodology, activity outputs may be incomplete. This is acceptable as long as:

- Incomplete items are recorded as `TODO` comments in the repository, **or**
- New change requests are created for the incomplete work within the current release
- All outputs will be reviewed during the [Final Verification](../release_activities/final_verification.md) before release

---

**Outputs:** Pull-request review (comments, checklist, approval/rejection)

**Verified by:** Not applicable

**Verification tasks:** Not applicable
