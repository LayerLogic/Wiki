## Issue - Reviewing Pull Requests

**Trigger:** Assignment to review a pull request

**Performed by:** The reviewer

**Inputs:** The content of the pull request

**Tasks:**

1. **Identify Activities Performed**

    Using the pull request description and the content of the changes, determine which activities were performed and which were performed partially or completely. If it's unclear, ask the pull-request author for clarification.

2. **Determine Appropriateness**

    - Determine whether you're an appropriate person to perform the verification. 
    
    For example. For example, if an activity specifies that the project lead should perform the verification, and you're not the project lead, then request that the project lead perform the review.

    - If you're reviewing code that can lead to severe harm and you aren't familiar with the code or don't have enough time to perform a necessarily thorough review, then request that someone else perform the review.

3. **Perform Verification Activities**

    Step through the verification tasks for the performed activities [[62304:5.5.3]]. Record the tasks you perform in the review response. We recommend using a markdown checklist. Such a list may look like this:

    ```
    - [x] Documents and implements software requirements
    - [x] Updates design specifications
    - [ ] Code construction follows the project standards
    - [ ] Unit, integration, or manual tests are updated
    - [ ] New sequences of events have been recorded
    ```

    Most git hosts have features that let you save standard replies. We suggest using these.

    It's okay to skip some common and low-risk verification tasks in this list. For example, there's no need to note that the "Git Commit Messages Include Change Request Numbers" verification task was performed for each commit.

4. **Write Feedback**

    Write detailed feedback. Ask questions before making suggestions. Compliment good work!

    If comments will be useful long after the review, consider suggesting that they be added to the documentation or code comments.

    You don't always need to leave comments. Sometimes there is nothing to say. It can be helpful to distinguish the case where you were too busy to do an in-depth review from an in-depth review that didn't result in any comments. In the latter case, it's helpful to comment on what you reviewed and any questions you asked yourself.

    If you're surprised by a change, ask the author why they did something a certain way. Sometimes there's a good reason you hadn't thought of, but even when there isn't, a Socrates-style sequence of questions can teach better than dictates. On the other hand, there's not always time for dialectic.

5. **Sign Off**

    If you're satisfied with the changes, approve the pull request [[62304:8.2.4.c]]. If there are important changes that must be made before the code can be merged, indicate this.

    Often the activity outputs will be incomplete. This often occurs since we're using an agile methodology. All activity outputs will be reviewed during the final release verification activity. However, if there are incomplete activity outputs, be sure they're recorded either as "TODO" comments within the repository or as new change requests within the current release.

    If the suggested changes are low-risk, it's okay to approve the pull request before the author implements them. This avoids another round-trip of approvals for a small change.

**Outputs:** Pull-request review

**Verified by:** Not applicable

**Verification tasks:** Not applicable