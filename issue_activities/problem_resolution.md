## Issue — Problem Resolution

> How to investigate, resolve, and document reported problems and defects.

---

**Trigger:** You're assigned a problem report (GitHub issue tagged with `bug` label)

**Performed by:** Assigned engineer

**Inputs:** The problem report (GitHub issue)

---

### Tasks

#### 1. Investigate

Investigate the problem and, if possible, identify the root cause [[62304:9.2.a, 62304:9.2.c]].

Record the following in the problem report:

- [ ] **Root cause** (or best hypothesis if uncertain)
- [ ] **Affected software items** — which modules/components are involved
- [ ] **Severity assessment** — Critical / High / Medium / Low
- [ ] **Reproducibility** — Always / Sometimes / Rare / Unable to reproduce

#### 2. Assess Impact

Evaluate the impact of the problem:

- [ ] **Safety impact** — Could this problem lead to a hazardous situation? If so, reference the relevant entry in the [Risk Management file](../plans/software_risk_management.xlsx).
- [ ] **User impact** — How many users are affected? Is there a workaround?
- [ ] **Data impact** — Could data be lost or corrupted?

#### 3. Advise Relevant Parties

If the problem affects devices/software that has been released:

- [ ] Notify the project lead and product owner
- [ ] Ensure appropriate people have enough information to decide whether and how to notify affected parties, including users and regulators
- [ ] Record **who** you notified in the problem report

[[62304:9.3, 62304:6.2.5.a, 62304:6.2.5.b — details regarding who to inform and how they should be informed are handled in other processes; software engineers must pass along the appropriate details.]]

#### 4. Fix or Defer

**If deferring (no fix needed):**

- [ ] Record the rationale for not taking action [[62304:9.2.d]]
- [ ] Discuss with the project lead as appropriate
- [ ] Note: unaddressed problem reports are included in most regulatory submissions

**If fixing:**

- [ ] Create a pull request that fixes the issue
- [ ] The GitHub issue containing the problem report also acts as the change request
- [ ] Include an automated test that **fails before** the fix and **passes after** the fix (if feasible)
- [ ] If automated testing is not feasible, record in the PR how it was verified that the problem is resolved
- [ ] Ensure the pull request references the problem report [[62304:8.2.4.a, 62304:8.2.4.b]]

---

**Outputs:** Completed problem report and either a fix (merged PR) or documented justification for deferral

**Verified by:** Another engineer

### Verification Tasks

1. **Root Cause Analysis** — Verify that the root cause investigation is thorough and the identified cause is plausible.
2. **Fix Completeness** — If a fix was implemented, verify that:
   - [ ] The fix addresses the root cause, not just the symptom
   - [ ] A regression test exists (or justification for why one is not feasible)
   - [ ] The PR references the problem report
3. **Impact Assessment** — Verify that the impact and severity were appropriately assessed.
4. **Notification** — If the problem affects released software, verify that the appropriate parties were notified.
5. **Deferral Justification** — If the problem is deferred, verify that the rationale is documented and appropriate.
