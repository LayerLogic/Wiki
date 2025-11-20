**Trigger:** Need to create a public release

**Performed by:** Project lead

**Inputs:** Code and documentation changes since the last release

**Tasks:**

If deficiencies are found while performing this activity, create change requests to address them.

1. **Release Verification**

   Complete these verification steps, filling in the release record that was started during the [Release - Planning activity](#release---planning):

   - Search the codebase and documentation for the sequence "TODO" comments. Address any that must be fixed prior to this release. None of them need to be fixed for this release. Address any comments
   - Review change requests in GitHub. Check that all planned change requests have been implemented and integrated [[62304:5.6.2.a, 62304:5.6.2.b and 62304:9.7.c]]. If there are unimplemented change requests, either move them to the next release or implement them prior to continuing the release activity.
   - Review outstanding problem reports. Confirm that none of the known anomalies result in unacceptable risk [[62304:5.8.3, and 62304:5.8.4]]. Confirm that any problem reports that were fixed are closed [[62304:9.7.a]].
   - The outputs of each activity are in a consistent state [[62304:5.1.6.c, 62304:5.1.6.d, and 62304:5.8.6]].
   - The unit tests adequately verify the software units [[62304:5.5.2]]. If not, create a change request to write unit tests to fill the gaps.
   - The integration tests adequately verify the software system [[62304:5.6.5 and 62304:5.7.4.c]]. If not, create a change request to write integration tests to fill the gaps.
   - All software requirements can be traced to appropriate verification [[62304:5.7.4.a, 62304:5.7.4.b, 62304:5.7.4.d]].
   - Read through the SDS. Make sure it is accurate and appropriately complete. If not, create a change request specifying the gaps that need to be filled.
   - The Release History Document is up-to-date.

2. **Integration and Testing**

   Follow the [Release - Software System Testing activity](#release---software-system-testing) and complete the test record [[62304:5.6.3, 62304:5.8.1, 62304:8.2.3]]. Verify that the test results meet the required pass/fail criteria [[62304:5.7.4.d]]. If anomalies are found, fix them and restart the release process [[62304:7.3.3.d 62304:5.8.1 62304:5.5.5]]].

3. **Tag the Release Git Commit**

   TODO: fill in the versioning scheme for this particular project

   Following the versioning scheme specified in the [Configuration Management Plan](#configuration-management-plan), determine the correct version.

   [Tag](https://git-scm.com/book/en/v2/Git-Basics-Tagging) the git commit that was used to build the release with this tag. (Note that the documents will be updated in a later commit.)

4. **Archive the Release Build Artifacts**

   [[:This activity addresses 62304:6.3.2, since development releases and maintenance releases are treated equivalently]]

   TODO: write out the details of where we will archive the build artifacts

   The purpose of the archive is to provide a means to re-test problems that may occur in an old version of the software.

   Archived releases shall be kept indefinitely.

5. **Complete the Release Record**

   Sign and fill in the release record.

   Compile the documents into PDFs, add them to the project file in share point.

6. **Archive the Release Documents**

   [[:This section fulfills 62304:5.8.7.a and 62304:5.8.7.b; note that documentation and configuration items are archived automatically due to the fact that they are stored in the git repository.]]

**Outputs:** Archived software release artifacts, release record, and documentation

**Verified by:** Not Applicable

**Verification tasks:** Not Applicable
