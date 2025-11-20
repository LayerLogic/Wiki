**Trigger:** You're assigned a problem report

**Performed by:** Engineer

**Inputs:** The problem report

**Tasks:**

1. Investigate

   Investigate the problem and, if possible, identify the cause and record it in the problem report [[62304:9.2.a and 62304:9.2.c]]. If possible, also note which software items were involved.

2. Advise Relevant Parties

   If the problem affects devices that have been released, make sure the appropriate people are aware of the situation and have enough information to decide whether and how to notify affected parties, including users and regulators---record who you notified in the problem report.

   [[62304:9.3 62304:6.2.5.a and 62304:6.2.5.b details regarding who to inform and how they should be informed are assumed to be handled in other processes, and that all that the software engineers must do is pass along the appropriate details.]]

3. Fix or Defer

   If there's no need to fix the issue, either because it doesn't impact safety or otherwise, record the rationale for not taking any action [[62304:9.2.d]]. Discuss with the project lead as appropriate. Note that unaddressed problem reports are included in most regulatory submissions.

   If you do fix the issue, then create a pull request that fixes it. The GitHub issue that contains the problem report can also act as the corresponding change request.

   If feasible, include an automated test that fails prior to the fix and passes after the fix. If not feasible, record how it was verified that the problem was resolved. Also, be sure the pull request references the problem report [[62304:8.2.4.a and 62304:8.2.4.b]].

**Outputs:** Completed problem report and either a fix or justification as to why a fix was unnecessary

**Verified by:** Another engineer

**Verification tasks:**

TODO: Add verification tasks & problem report template reference
