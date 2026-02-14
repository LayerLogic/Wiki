## Issue — Creating Pull Requests

> The complete workflow for branching, committing, and merging code changes.

---

**Trigger:** Need to change documentation, code, or other files

**Performed by:** Whoever is making the change

**Inputs:** An approved change request (GitHub issue) and the relevant codebase

---

### Tasks

#### 1. Identify Change Request

All changes must tie back to a change request [[62304:8.2.1]]. There **must** be an approved change request (GitHub issue assigned to the current release) before you begin work.

#### 2. Create Git Branch

Create a new git branch from `main`. The branch name **must** begin with the change request number:

```
# Single change request
git checkout -b 104-short-description

# Multiple change requests
git checkout -b 104-132-short-description
```

#### 3. Create Git Commits

Create git commits of logically related sets of changes as you make progress [[62304:5.1.1.d, 62304:6.1.e, 62304:8.2.2]].

**Commit message format:**

```
<Title line — max 50 characters, capitalised, no period>

<Body — explain WHAT and WHY, not HOW. Wrap at 72 characters.>

Issue #104
```

**Guidelines:**

- Separate subject/title from body with a blank line
- Use the body to explain **what** and **why**, NOT how
- Limit the subject/title line to 50 characters
- Capitalise the subject/title line
- Do not end the subject/title line with a period
- Wrap the body at 72 characters
- Every commit **must** include a reference to the change request (e.g., `Issue #104`)

Push your commits to GitHub periodically to back up your work.

#### 4. Create Pull Request

When work on the change request(s) is nearing completion, create a GitHub pull request for merging your branch into `main`. Use the [Pull Request Template](../.github/pull_request_template.md) — it will auto-populate when you create the PR.

The PR description should include:

- A brief point-wise summary of the changes
- The change request number(s) addressed
- Any special testing instructions
- Screenshots or recordings for UI changes

#### 5. Assign Pull Request Reviewer

Select a reviewer (or multiple reviewers) as appropriate for the activities you performed. Each activity indicates who must verify the outputs.

**Important exceptions:**

- If a review must be skipped due to absence or internal deadlines, the engineer **must** justify why in the PR comments **and** create a TODO/change request to ensure verification occurs before the next release.
- If someone outside the core development team reviews the PR, mention who performed the review in the PR body and apply the `external-review` label.

#### 6. Address Review Comments

- **Never ignore comments entirely.** If you disagree with a suggestion, make your case with a clear rationale.
- Once an issue is resolved, "thumbs up" or write "fixed" on the originating comment to confirm resolution.
- If the PR was not approved, request a new review once comments have been addressed.

#### 7. Merge the Pull Request

- Merge the pull request into `main`, resolving any conflicts [[62304:5.1.5, 62304:5.6.1]].
- **Delete the branch** in GitHub after successful merge.
- Confirm that CI/CD checks pass on `main` after the merge.

---

**Outputs:** Changes merged into the main branch

**Verified by:** Depends on the changes (see individual activity verification requirements)

### Verification Tasks

1. **Pull Request Message** — Verify that the PR description accurately describes the changes.
2. **Git Commit Messages Include Change Request Numbers** — Verify that all commit messages reference the appropriate change request numbers.
3. **Git Commit Message Content** — Verify that commit messages follow the guidelines above.
4. **CI/CD Checks** — Verify that all automated checks pass on the PR.
