**Trigger:** Need to create a software system test record

**Performed by:** An engineer

**Inputs:** The build artifacts to test

**Tasks:**

1. **Start Test Record**

   Copy `documents/test_record_template.md` and name it appropriately. (Usually, it makes sense to name test records after the release they're testing.)

   Add your name to the test record [[62304:5.6.7.c and 62304:5.7.5.c and 62304:9.8.g]].

   Add the date when you started the testing [[62304:9.8.f]].

2. **Unit and Integration Tests**

   Although it's usually impossible to run the unit and integration tests in a production environment, the test environment should match the production environment as closely as possible. The test record should describe the test environment and should be detailed enough to allow another engineer to re-run the tests [[62304:5.6.7.b and 62304:5.7.5.b]]. In particular, it should include the git commit hash for the state of the code that was built and tested [[62304:9.8.c]]. Dirty working environments aren't allowed. Any relevant environment variables should also be included. Any testing tools [[62304:9.8.e]] or hardware should also be recorded [[62304:9.8.d]].

   Run the unit and integration tests. Include the list of tests that were run and whether they passed or failed [[62304:5.6.7.a 62304:5.7.5.a]].

3. **Manual System Testing**

   The manual tests will be run on a staging environment that is as similar to the production environment as possible. The test record should describe the staging environment and should be detailed enough to allow the tests to be re-run [[62304:5.6.7.b and 62304:5.7.5.b]].

   {# NOTE that this approach assumes that the engineer will be running the manual tests. Chances are there will be additional testing that occurs above the software level. It may make sense to refer to this higher-level testing as the "system testing" and leave it to the higher-level documentation. #}

   Run the manual tests. Include the list of tests that were run and whether they passed or failed [[62304:5.6.7.a 62304:5.7.5.a]].

4. **Reporting Test Failures**

   Any test failures shall be recorded as problem reports [[62304:5.6.8 62304:5.7.4.d]]. See the [prepare problem report activity](#prepare-problem-report) for details [[62304:5.7.2]]. If any pull requests are implemented in response to these problem reports, the tests must be re-run [[62304:5.7.3.a 62304:5.7.3.b]]. If it is deemed unnecessary to re-run some of the tests, the justification as to why shall be included in the test record.

5. **Completing the Test Record**

   Finish filling in the rest record. Be sure it records whether the overall test-run passes or fails according to the criteria listed in the [Testing Plan](#testing-plan) [[62304:5.6.7.a 62304:5.6.4]].

**Outputs:** Completed test record and any problem reports

**Verification tasks:**

1. **Review Test Record**

   Ensure the test record is completed correctly:

   - Check that all of the tests have been run.
   - Confirm that there is enough detail to recreate the test environment.
   - Confirm that the overall test-run result is consistent with the [Testing Plan](#testing-plan).
