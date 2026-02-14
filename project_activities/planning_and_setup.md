## Project — Planning & Setup

> One-time setup activities when starting a new project.

---

**Trigger:** Start of a new project

**Performed by:** Project Lead

**Inputs:** User needs and system requirements

---

### Tasks

#### 1. GitHub Repository Setup

Set up a git repository on GitHub with the following configuration:

**Branch Protection (for `main` branch):**

- [ ] Disable [forced pushes](https://git-scm.com/docs/git-push#Documentation/git-push.txt--f) — ensures project history cannot be overwritten
- [ ] Require [signed commits](https://git-scm.com/book/en/v2/Git-Tools-Signing-Your-Work) — ensures code changes can be traced to the person who made them
- [ ] Require pull-request reviews before merging (at least 1 approval)
- [ ] Require status checks to pass before merging (CI/CD)

**Issue Labels:**

Create the following labels:

| Label             | Color     | Description                                   |
| ----------------- | --------- | --------------------------------------------- |
| `bug`             | 🔴 Red    | Problem reports and defects                   |
| `feature`         | 🟢 Green  | New feature requests                          |
| `enhancement`     | 🔵 Blue   | Improvements to existing features             |
| `documentation`   | 📄 Grey   | Documentation-only changes                    |
| `obsolete`        | ⚫ Black  | Issues that are no longer relevant            |
| `external-review` | 🟡 Yellow | PRs reviewed by someone outside the core team |

**Milestones:**

- Create a milestone named **"icebox"** — used to tag issues that may be included in future releases but are not currently prioritised.

**Templates:**

- Add the [Bug Report](.github/ISSUE_TEMPLATE/bug_report.yaml) issue template
- Add the [Feature Request](.github/ISSUE_TEMPLATE/feature_request.yaml) issue template
- Add the [Change Request](.github/ISSUE_TEMPLATE/change_request.yaml) issue template
- Add the [Pull Request Template](.github/pull_request_template.md)

#### 2. CI/CD Pipeline Setup

Configure a CI/CD pipeline (e.g., GitHub Actions) that:

- [ ] Runs linters and static analysis on every push
- [ ] Runs unit tests on every push
- [ ] Runs integration tests on every pull request
- [ ] Blocks merging if any checks fail
- [ ] Reports code coverage

#### 3. Development Standards

Document the project's development standards:

- [ ] Programming language(s) and versions
- [ ] Code style guide / linting configuration
- [ ] Naming conventions
- [ ] Commit message format (see [Creating Pull Requests](../issue_activities/creating_pull_requests.md))
- [ ] Branching strategy
- [ ] Dependency management approach

#### 4. Software Plan Review

Read through the software plan (this wiki). Fix any typos, correct outdated information, and verify all links work.

---

**Outputs:** The hosted git repository, CI/CD pipeline, and configured software plan

**Verified by:** Project Lead

### Verification Tasks

1. **Proof-Read Plan** — Read through the software plan. Fix any typos. Correct any outdated information. Check that all links work.

2. **Activity Specification** — Ensure each activity specification includes:
   - [ ] The activity's trigger events
   - [ ] Which roles should perform the activity
   - [ ] Its inputs
   - [ ] Its tasks [[62304:5.1.1.a]]
   - [ ] Its outputs [[62304:5.1.1.b, 62304:5.1.6.a]]
   - [ ] Who should verify the outputs
   - [ ] The verification tasks [[62304:5.1.6.b]] along with their acceptance criteria [[62304:5.1.6.d]]

3. **Repository Configuration** — Verify that:
   - [ ] Branch protection rules are active
   - [ ] Issue templates are configured
   - [ ] CI/CD pipeline runs on PRs

---

**Comments:**

Keep this planning document up to date as the project progresses [[62304:5.1.2]], and step through the verification tasks whenever there are process changes.

All software activity outputs will be stored in this git repository, the associated GitHub issues, or the associated GitHub pull requests, unless explicitly noted otherwise [[62304:5.1.1.b]]. Problem reports and change requests are stored as GitHub issues. A GitHub issue tagged with the `bug` label is a problem report. If a problem report outlines a set of requested changes, then it can simultaneously act as a change request. GitHub issues tagged with the `obsolete` label are ignored.

The software engineers working on the project are responsible for keeping all software activity outputs within version control at the times specified in the activity descriptions [[62304:5.1.9.c, 62304:5.1.9.d, 62304:5.1.9.e]].
