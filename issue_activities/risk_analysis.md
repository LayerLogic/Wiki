## Issue — Risk Analysis

> How to identify, document, and verify risks when software items change.

---

**Trigger:** Software items are added, removed, or their architecture is modified

**Performed by:** Engineer implementing, or planning for, the change

**Inputs:** The design specification (SDS) and system-level risk analysis

---

### Tasks

#### 1. Identify Existing or New Hazardous Situations

Review the [Risk Management file](../plans/software_risk_management.xlsx) and consider:

- Can the software modules being worked on contribute to any of the hazardous situations **already listed**?
- Can you think of hazardous situations that are **not yet listed**?

If new hazardous situations are identified, record them in the [Risk Management file](../plans/software_risk_management.xlsx) with:

- A sequential Hazard ID following the format `SAF-XXX` (where `XXX` is a three-digit unique ID continuing from the last documented ID, starting from `001`)
- A clear description of the hazardous situation
- The affected software items

#### 2. Document Sequences of Events

If any hazardous situations were identified, document the sequences of events that may lead to them in the [Risk Management file](../plans/software_risk_management.xlsx).

> **Note:** Although IEC 62304 distinguishes between "sequences of events leading to a hazardous situation" and "software causes of a hazardous situation," we consider the "cause" to be the penultimate event in the sequence and do not distinguish them separately in our documentation.

When enumerating sequences of events, consider:

- [ ] Incorrect or incomplete specifications of functionality [[62304:7.1.2.a]]
- [ ] Software defects in the code being added or modified [[62304:7.1.2.b]]
- [ ] Failures or unexpected results from new or existing dependencies (SOUP) [[62304:7.1.2.c]]
- [ ] Hardware failures [[62304:7.1.2.d]]
- [ ] Other software defects that could result in unpredictable software operation [[62304:7.1.2.d]]
- [ ] Reasonably foreseeable misuse [[62304:7.1.2.e]]
- [ ] Unreliable network connections
- [ ] Cybersecurity vulnerabilities
- [ ] Interference with existing risk control measures documented in the [Risk Management file](../plans/software_risk_management.xlsx) [[62304:7.4.2]]

> **Guidance:** Only be as detailed as is useful for improving the software. Over-documentation without actionable insight adds cost without value.

#### 3. Define Risk Control Measures

For each identified hazardous situation, propose risk control measures. Document them in the [Risk Management file](../plans/software_risk_management.xlsx) with:

- A description of the control measure
- The implementation status (Planned / Implemented / Verified)
- The residual risk level after the control measure is applied

---

**Outputs:** Updates to the [Risk Management file](../plans/software_risk_management.xlsx)

**Verified by:** Another engineer

### Verification Tasks

1. **Review Completeness** — Consider whether all relevant sequences of events were captured. Review that the granularity of the sequences of events is appropriate. Verify that all columns are filled appropriately for each documented hazard.

2. **Review Traceability** — Confirm that the following can be traced together [[62304:7.3.3.a, 62304:7.3.3.b, 62304:7.3.3.c, 62304:7.3.3.d]]:
   - [ ] Software item(s)
   - [ ] Sequence(s) of events
   - [ ] Hazardous situation(s)
   - [ ] Risk control measure(s)

3. **Review Risk Control Measures** — Verify that proposed risk control measures are reasonable and sufficient to reduce risk to acceptable levels.
