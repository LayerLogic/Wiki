**Trigger:** Start of a new project

**Performed by:** Project Lead

**Inputs:** User needs and system requirements

**Tasks:**

1. **GitHub Repository Setup**

   Set up a git repository on GitHub.

   Configure GitHub to disable [forced pushes](https://git-scm.com/docs/git-push#Documentation/git-push.txt--f). This ensures users can't overwrite the project history.

   Configure GitHub to only accept [signed commits](https://git-scm.com/book/en/v2/Git-Tools-Signing-Your-Work). Signed commits ensure that code changes can be traced back to the person who made the changes.

   Configure GitHub to require pull-request reviews as appropriate.

   Create the following issue labels:

   - Bug
   - Obsolete

   Create a GitHub milestone that is named "icebox". This milestone will be used to tag issues that may be included in future releases.

   Consider adding a GitHub issue template to enforce the format for problem reports.

**Outputs:** The updated software plan document and the hosted git repository

**Verified by:** Project Lead

**Verification tasks:**

1. **Proof-Read Plan**

   Read through the software plan. Fix any typos. Correct any outdated information. Check that all the links work.

2. **Activity Specification**

   Ensure each activity specification includes

   - the activity's trigger events
   - which roles should perform the activity
   - its inputs
   - its tasks [[62304:5.1.1.a]]
   - its outputs [[62304:5.1.1.b 62304:5.1.6.a]]
   - who should verify the outputs
   - the verification tasks [[62304:5.1.6.b]] along with their acceptance criteria [[62304:5.1.6.d]].

**Comments:**

Keep this planning document up to date as the project commences [[62304:5.1.2]], and step through the verification tasks whenever there are process changes.

All software activity outputs will be stored in this git repository, the associated GitHub issues, or the associated GitHub pull requests, unless explicitly noted otherwise [[62304:5.1.1.b]]. Problem reports and change requests are stored as GitHub issues. A GitHub issue tagged with the `bug` label is a problem report. If a problem report outlines a set of requested changes, then it can simultaneously act as a change request. GitHub issues tagged with the `obsolete` label are ignored.

The software engineers working on the project are responsible for keeping all software activity outputs within version control at the times specified in the activity descriptions [[62304:5.1.9.c, 62304:5.1.9.d, and 62304:5.1.9.e]].
