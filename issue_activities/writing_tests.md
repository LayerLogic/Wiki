## Issue — Writing Tests

> How to evaluate, implement, and verify tests for requirements and risk controls.

---

**Trigger:** Requirements are added or changed, the risk analysis changes, verifying the fix for a problem report, or as needed

**Performed by:** Engineer implementing a change

**Inputs:** The requirements (SRS), risk analysis, or the problem report

---

### Tasks

#### 1. Evaluate Test Type

Review the [Testing Plan](../plans/testing_plan.md). Determine what types of tests are appropriate for the changes you're making:

| Test Type               | When to Use                                                                     |
| ----------------------- | ------------------------------------------------------------------------------- |
| **Unit tests**          | New or modified functions, classes, or modules                                  |
| **Integration tests**   | Changes to interfaces between software items, APIs, or external systems         |
| **Manual system tests** | User-facing features, UI changes, or workflows that cannot be fully automated   |
| **Regression tests**    | Whenever fixing a bug — write a test that fails before the fix and passes after |

#### 2. Implement Tests

Implement tests as appropriate. Ensure all tests are **passing** before submitting for review [[62304:5.5.5]].

**Best practices:**

- [ ] Write tests that are **readable** — another engineer should understand what's being tested and why
- [ ] Write tests that are **deterministic** — avoid flaky tests that depend on timing, order, or external state
- [ ] Write tests that are **fast** — slow tests discourage running them frequently
- [ ] Follow the **Arrange-Act-Assert** pattern for unit tests
- [ ] For bug fixes, write a test that **reproduces the bug first**, then fix the code

#### 3. Traceability

Each requirement **must** have at least one test to verify it [[62304:5.7.4.a]]. Document the requirement-to-test mapping using:

- Comments in the test code referencing the requirement ID (e.g., `// Verifies REQ-042`)
- The `Requirement IDs` column in the [Test Record](../release_activities/test_record.md) (during release)

---

**Outputs:** New or updated tests (unit, integration, or manual test scripts)

**Verified by:** Another engineer (during pull request review)

### Verification Tasks

1. **Evaluate Completeness** — Are the requirements adequately covered by the new tests? Are there edge cases or error conditions that should be tested?

2. **Evaluate Utility** — Are the tests robust or overly fragile? Will they break due to unrelated changes? Are they fast enough to run frequently?

3. **Evaluate Traceability** — Does each test reference the requirement(s) it verifies? Are all new requirements covered?
