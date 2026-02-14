## Project — Initial Risk Analysis

> How to perform the initial system-level risk analysis at the start of a project.

---

**Trigger:** Start of a new project

**Performed by:** Software development team with the project lead

**Inputs:** Draft SRS, Draft SDS, and other relevant documents

---

### Tasks

#### 1. Initial Risk Analysis

Perform an initial risk analysis taking into account the initial architectural design and software requirements [[62304:5.2.4]].

The risk analysis must be documented in the [Risk Management file](../plans/software_risk_management.xlsx) and include:

- [ ] **Identified hazards** — what can go wrong?
- [ ] **Hazardous situations** — circumstances where people, property, or environment are exposed to hazards
- [ ] **Sequences of events** — how could a hazard lead to harm?
- [ ] **Initial risk control measures** — what can be done to reduce the risk?
- [ ] **Residual risk assessment** — is the remaining risk acceptable?

> **Important:** The resulting risk analysis must include identifiable hazards and hazardous situations so that software engineers can perform their [issue-level risk analysis activities](../issue_activities/risk_analysis.md) throughout development.

#### 2. Risk Classification

For each identified risk, assess and document:

| Factor          | Classification                                                       |
| --------------- | -------------------------------------------------------------------- |
| **Severity**    | Negligible / Minor / Serious / Critical / Catastrophic               |
| **Probability** | Improbable / Remote / Occasional / Probable / Frequent               |
| **Risk Level**  | Acceptable / ALARP (As Low As Reasonably Practicable) / Unacceptable |

#### 3. Share with Team

Once complete:

- [ ] Link the risk analysis to the project's SDS
- [ ] Share with the management team and product owner
- [ ] Review findings with the engineering team during a planning session

---

**Outputs:** Risk analysis draft in the [Risk Management file](../plans/software_risk_management.xlsx), including hazards, hazardous situations, and initial risk control measures

**Verified by:** Project Lead

### Verification Tasks

1. **Completeness** — Verify that all major system components have been considered for risk.
2. **Severity Assessment** — Verify that risk classifications are appropriate.
3. **Risk Control Measures** — Verify that proposed mitigations are reasonable and feasible.
