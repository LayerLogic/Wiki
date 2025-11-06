**Trigger:** The start of a new release

**Performed by:** Project lead

**Inputs:** User needs, Draft SRS, Draft SDS, and Problem Reports

**Tasks:**

1. **Select Version Number**

   Each release shall have a version number.

   TODO: add more details about project versioning here. E.g., you may want to follow [semver](https://semver.org).

   version number MAJOR.MINOR.PATCH, incrementing the:

   - MAJOR version when you make incompatible API changes
   - MINOR version when you add functionality in a backward compatible manner
   - PATCH version when you make backward compatible bug fixes

2. **Release Setup**

   Create the GitHub milestone for the release.

3. **Start a New Release Record**

   Make a copy of the Release Record and Test Record templates and fill in as much detail as is appropriate; these will be filled in before the release is finalized.

4. **Review Software Dependencies**

   If the release is public, determine if any software dependencies have become obsolete or should be upgraded. Also, review known anomalies in published anomalies lists as appropriate [[62304:6.1.f]].

   Create change requests as appropriate.

5. **Review Problem Reports**

   Consider outstanding problem reports in the backlog [[62304:9.4]]. Move problem reports into the current release as appropriate.

6. **Review Risk Management File**

   Review {{workflow.risk_management_file}} for risk control measures that have not been implemented [[62304:7.2.2.c]].

   Create change requests as appropriate.

7. **Add Initial Change Requests**

   Coordinate with the product owner regarding which features should be included in the release. Create change requests for the major new features as appropriate.

   Create change requests as appropriate.

**Outputs:** A partially completed release record and the set of change requests which should be implemented for the next release

**Verified by:** Project lead

**Verification tasks:**

1. **Release Record**

   Be sure you've fully updated the new release record template.
