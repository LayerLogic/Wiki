## Issue - Writing Tests

**Trigger:** Requirements are added or changed, the risk analysis changes, verifying the fix for a problem report, or as needed

**Performed by:** Engineer implementing a change

**Inputs:** The requirements and risk analysis or the problem report

**Tasks:**

1. **Evaluate Test Type**

    Review the [Testing Plan](../plans/testing_plan.md). Determine what types of tests are appropriate for the changes you're making.

2. **Implement Tests**

    Implement tests as appropriate. Ensure they're passing [62304:5.5.5, excluding documenting the result which is handled elsewhere].

3. **Traceability**

    Each requirement must have at least one test to verify it.

**Outputs:** Tests

**Verified by:** Another engineer

**Verification tasks:**

1. **Evaluate Completeness**

    Evaluate whether the requirements are covered by the new tests.

2. **Evaluate Utility**

    Evaluate whether the tests will be overly fragile. Ensure they're not too slow.
