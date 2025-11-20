## Issue - Creating Pull Requests

**Trigger:** Need to change documentation, code, or other files

**Performed by:** Whoever is making the change

**Inputs:** Varies depending on the change

**Tasks:**

1. **Identify Change Request**

    All changes must tie back to a change request [[62304:8.2.1]]. Therefore, there should be a change request before you begin work.

2. **Create Git Branch**

    Create a new git branch. The name should begin with the change request number, e.g., `104-short-description`. If you are working on multiple change requests at once, you can include both numbers in the name at the beginning, e.g., `104-132-short-description`.

3. **Create Git Commits**

    Create git commits of logically related sets of changes as you make progress [[62304:5.1.1.d, 62304:6.1.e and 62304:8.2.2]]. Write commit messages with varying levels of detail, as appropriate. Typically, early on in a project, thorough git commit messages are less worthwhile. As the project stabilizes (and especially after the first public release), commit messages become more important.

    Guidelines for writing commit messages:

    - Separate subject/title from body with a blank line
    - Use the body to explain what and why, NOT how
    - Limit the subject/title line to 50 characters
    - Capitalize the subject/title line
    - Do not end the subject/title line with a period
    - Wrap the body at 72 characters

    All commits should include a link back to the change request. E.g., `Issue #104`. However, if you're working on another change request within your current branch, that's okay---just be sure to update the numbers.

    Push your commits to GitHub periodically to back up your work.

4. **Create Pull Request**

    When work on the change request(s) is nearing completion, a GitHub pull request should be created for merging your git branch into the main branch. A brief point-wise summary of the changes should be included in the merge request description. These comments will be included in the release history record.

5. **Assign Pull Request Reviewer**

    Once you're ready for your changes to be reviewed, you must assign a reviewer to verify the changes. Select a reviewer (or multiple reviewers) as appropriate for the activities you performed. Each activity indicates who must verify the outputs. E.g., some activities require that the project lead be the reviewer.

    Occasionally, due to the absence of other reviewers or due to an internal testing deadline, it may be necessary to skip the pull request review. When this happens, the engineer should justify why a review wasn't necessary within the merge request comments or create a change request or a "TODO" to ensure verification occurs before the next release.

    If, as is occasionally appropriate, someone outside of the core development team reviews a pull request, then mention who performed the review in the merge request body and tag the merge request with the `external-review` label.

6. **Addressing Comments**

    Do not ignore comments entirely. If you disagree with a suggestion, then make your case. If you think a refactor would make the code better but isn't necessary, then make your case.

    Once an issue is resolved, it's best to "thumbs up" or write "fixed" in the comment that requested the change. Sometimes, fixing the issue and pushing the change is insufficient because there might be a mismatch between what the reviewer thinks is being suggested and what the author does to address the suggestion. In this situations one person may think they've addressed an issue while another person hasn't.

    If the pull request wasn't approved, request a new review once the comments have been addressed.

7. **Merging the Request**

    Merge the pull request into the main branch, resolving any conflicts that arise. Once the branch has been merged successfully, delete the branch in GitHub [[62304:5.1.5 and 62304:5.6.1]].

**Outputs:** Changes merged into the main branch

**Verified by:** Depends on the changes

**Verification tasks:**

1. **Pull Request Message**

    Verify that the pull request's message describes the changes.

2. **Git Commit Messages Include Change Request Numbers**

    Verify that all of the git commit messages include change request numbers.

3. **Git Commit Message Content**

    Verify that the git commit messages are appropriate (see comments above).