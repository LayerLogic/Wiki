## Release — Software System Testing

> How to execute and record unit, integration, and manual system tests for a release.

---

**Trigger:** Need to create a software system test record for a release

**Performed by:** An engineer

**Inputs:** The build artefacts to test

---

### Tasks

#### 1. Start Test Record

- [ ] Copy the [Test Record](./test_record.md) template and name it for the release (e.g., `test_record_v1.2.0.md`)
- [ ] Add your name to the test record [[62304:5.6.7.c, 62304:5.7.5.c, 62304:9.8.g]]
- [ ] Add the date when you started testing [[62304:9.8.f]]
- [ ] Record the git commit hash for the code being tested [[62304:9.8.c]]

#### 2. Unit and Integration Tests

> Although it's usually impossible to run unit and integration tests in a production environment, the test environment should match the production environment as closely as possible.

The test record should include enough detail for another engineer to reproduce the test environment [[62304:5.6.7.b, 62304:5.7.5.b]]:

- [ ] **Git commit hash** — the exact state of the code built and tested
- [ ] **Environment details** — OS, runtime versions, relevant environment variables
- [ ] **Clean working environment** — no uncommitted changes (dirty environments are not allowed)
- [ ] **Testing tools** used [[62304:9.8.e]]
- [ ] **Hardware** used (if applicable) [[62304:9.8.d]]

Run the tests and record results:

```bash
# Example: Run all tests in a clean environment
git checkout v1.2.0
npm ci          # Clean install of dependencies
npm run test    # Run unit and integration tests
```

- [ ] Record the list of tests that were run
- [ ] Record whether each test passed or failed [[62304:5.6.7.a, 62304:5.7.5.a]]
- [ ] Record code coverage metrics

#### 3. Manual System Testing

Manual tests should be run on a **staging environment** that mirrors production as closely as possible.

The test record must describe the staging environment in sufficient detail to allow the tests to be re-run [[62304:5.6.7.b, 62304:5.7.5.b]].

- [ ] Set up the staging environment (document the setup steps)
- [ ] Run each manual test case from the test plan
- [ ] Record whether each test step passed or failed [[62304:5.6.7.a, 62304:5.7.5.a]]
- [ ] Capture screenshots or evidence for key validation steps

#### 4. Reporting Test Failures

Any test failures **must** be recorded as problem reports (GitHub issues tagged with `bug`) [[62304:5.6.8, 62304:5.7.4.d]]. See the [Problem Resolution](../issue_activities/problem_resolution.md) activity for details [[62304:5.7.2]].

**If fixes are implemented:**

- [ ] All affected tests **must** be re-run [[62304:5.7.3.a, 62304:5.7.3.b]]
- [ ] If only a subset of tests is re-run, document the regression analysis justification in the test record

#### 5. Completing the Test Record

- [ ] Fill in all remaining fields in the test record
- [ ] Record whether the overall test run **passes** or **fails** according to the criteria in the [Testing Plan](../plans/testing_plan.md) [[62304:5.6.7.a, 62304:5.6.4]]
- [ ] Link all problem reports created during testing

---

**Outputs:** Completed test record and any problem reports

**Verified by:** Another engineer

### Verification Tasks

1. **Review Test Record** — Ensure the test record is completed correctly:
   - [ ] All planned tests have been executed
   - [ ] There is enough detail to recreate the test environment
   - [ ] The overall test-run result is consistent with the [Testing Plan](../plans/testing_plan.md) criteria
   - [ ] All test failures have corresponding problem reports
   - [ ] Any re-runs after fixes are documented with regression analysis
