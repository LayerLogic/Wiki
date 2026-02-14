## Release — Planning

> How to plan and set up a new software release.

---

**Trigger:** The start of a new release cycle

**Performed by:** Project Lead

**Inputs:** User needs, Draft SRS, Draft SDS, and Problem Reports

---

### Tasks

#### 1. Select Version Number

Each release shall have a version number following [Semantic Versioning (SemVer)](https://semver.org):

```
MAJOR.MINOR.PATCH
```

| Component | Increment When                                        |
| --------- | ----------------------------------------------------- |
| **MAJOR** | You make incompatible API changes or breaking changes |
| **MINOR** | You add functionality in a backward-compatible manner |
| **PATCH** | You make backward-compatible bug fixes                |

**Pre-release versions** may use suffixes: `1.0.0-alpha.1`, `1.0.0-beta.1`, `1.0.0-rc.1`

#### 2. Release Setup

- [ ] Create a GitHub milestone for the release (e.g., `v1.2.0`)
- [ ] Set the milestone's target date
- [ ] Create a release branch if using a release branching strategy (e.g., `release/1.2.0`)

#### 3. Start a New Release Record

- [ ] Copy the [Release Record](./release_record.md) template and name it for the release (e.g., `release_record_v1.2.0.md`)
- [ ] Copy the [Test Record](./test_record.md) template and name it for the release (e.g., `test_record_v1.2.0.md`)
- [ ] Fill in as much detail as is appropriate; these will be completed before the release is finalised

#### 4. Review Software Dependencies

If the release is public, review all software dependencies:

- [ ] Determine if any dependencies have become obsolete or should be upgraded
- [ ] Review known anomalies in published vulnerability databases [[62304:6.1.f]]
- [ ] Run dependency audit tools (e.g., `npm audit`, `pip audit`, `snyk test`)
- [ ] Create change requests for any necessary dependency updates

#### 5. Review Problem Reports

- [ ] Review outstanding problem reports in the backlog [[62304:9.4]]
- [ ] Move safety-critical problem reports into the current release
- [ ] Triage remaining problem reports by severity and priority

#### 6. Review Risk Management File

- [ ] Review the [Risk Management file](../plans/software_risk_management.xlsx) for risk control measures that have not been implemented [[62304:7.2.2.c]]
- [ ] Create change requests for any unimplemented risk controls that must be addressed in this release

#### 7. Add Initial Change Requests

- [ ] Coordinate with the product owner regarding which features should be included in the release
- [ ] Create change requests for major new features
- [ ] Ensure all change requests are assigned to the release milestone

---

**Outputs:** A partially completed release record and the set of change requests for the release

**Verified by:** Project Lead

### Verification Tasks

1. **Release Record** — Verify that the new release record template has been copied and partially filled in.
2. **Milestone** — Verify that the GitHub milestone exists with the correct version number and target date.
3. **Dependencies** — Verify that a dependency review was performed.
4. **Risk Controls** — Verify that unimplemented risk controls were reviewed.
