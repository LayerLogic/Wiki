## Release — Final Verification

> The comprehensive release verification checklist before making a release public.

---

**Trigger:** Need to create a public release

**Performed by:** Project Lead

**Inputs:** Code and documentation changes since the last release

---

### Tasks

> **Note:** If deficiencies are found while performing this activity, create change requests to address them before proceeding.

#### 1. Release Verification Checklist

Complete these verification steps, recording the results in the release record that was started during the [Release Planning](./planning.md) activity:

- [ ] **TODO Audit** — Search the codebase and documentation for `TODO` comments. Address any that must be fixed prior to this release. Document any that are intentionally deferred.

- [ ] **Change Request Review** — Review change requests in GitHub. Check that all planned change requests have been implemented and integrated [[62304:5.6.2.a, 62304:5.6.2.b, 62304:9.7.c]]. If there are unimplemented change requests, either move them to the next release or implement them before continuing.

- [ ] **Problem Report Review** — Review outstanding problem reports. Confirm that none of the known anomalies result in unacceptable risk [[62304:5.8.3, 62304:5.8.4]]. Confirm that fixed problem reports are closed [[62304:9.7.a]].

- [ ] **Activity Output Consistency** — Verify that the outputs of each activity are in a consistent state [[62304:5.1.6.c, 62304:5.1.6.d, 62304:5.8.6]].

- [ ] **Unit Test Adequacy** — Verify that unit tests adequately cover the software units [[62304:5.5.2]]. If gaps exist, create change requests to fill them.

- [ ] **Integration Test Adequacy** — Verify that integration tests adequately cover the software system [[62304:5.6.5, 62304:5.7.4.c]]. If gaps exist, create change requests to fill them.

- [ ] **Requirements Traceability** — Verify that all software requirements can be traced to appropriate verification (tests or other evidence) [[62304:5.7.4.a, 62304:5.7.4.b, 62304:5.7.4.d]].

- [ ] **SDS Review** — Read through the SDS. Ensure it is accurate and appropriately complete. If not, create change requests specifying the gaps.

- [ ] **Release History** — Verify that the release history document is up-to-date.

#### 2. Integration and Testing

- [ ] Follow the [Software System Testing](./software_system_testing.md) activity and complete the test record [[62304:5.6.3, 62304:5.8.1, 62304:8.2.3]]
- [ ] Verify that the test results meet the required pass/fail criteria (see [Testing Plan](../plans/testing_plan.md)) [[62304:5.7.4.d]]
- [ ] If anomalies are found, fix them and **restart the release process** [[62304:7.3.3.d, 62304:5.8.1, 62304:5.5.5]]

#### 3. Tag the Release Git Commit

Following the versioning scheme specified in the [Release Planning](./planning.md) activity (Semantic Versioning), determine the correct version number.

```bash
# Tag the release commit
git tag -a v1.2.0 -m "Release v1.2.0: <brief description>"
git push origin v1.2.0
```

> **Important:** Tag the git commit that was used to build the release. Documents may be updated in a later commit, but the tagged commit must be the one that produced the release artefact.

#### 4. Archive the Release Build Artefacts

[[This activity addresses 62304:6.3.2, since development releases and maintenance releases are treated equivalently]]

Archive the release build artefacts to provide a means to re-test problems that may occur in an old version:

- [ ] Build the release artefact from the tagged commit in a clean environment
- [ ] Upload the artefact to the designated archive location (e.g., GitHub Releases, cloud storage, or shared drive)
- [ ] Record the artefact checksum (SHA-256) in the release record
- [ ] Archived releases shall be kept **indefinitely**

#### 5. Complete the Release Record

- [ ] Sign the release record with the project lead's name and date
- [ ] Fill in all remaining fields in the release record
- [ ] Compile the documents into PDFs
- [ ] Add them to the project file in the designated storage location

#### 6. Archive the Release Documents

[[This section fulfils 62304:5.8.7.a and 62304:5.8.7.b; documentation and configuration items are archived automatically via the git repository.]]

- [ ] Verify that all release documents are committed to the git repository
- [ ] Create a GitHub Release with the release notes and linked artefacts

---

**Outputs:** Archived software release artefacts, completed release record, and documentation

**Verified by:** Not applicable (self-verified by project lead during the process)

**Verification tasks:** Not applicable
