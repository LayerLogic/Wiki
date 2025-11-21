## Issue - Risk Analysis

**Trigger:** Software items are added, removed, or their architecture is modified

**Performed by:** Engineer implementing, or planning for, the change

**Inputs:** The design specification and system-level risk analysis

**Tasks:**

1. **Identify Existing or New Hazardous Situations**

    Can the software modules being worked on contribute to any of the hazardous situations listed in [Risk Management](../plans/software_risk_management.xlsx)?

    Can you think of hazardous situations that are not listed? If so, record them in [Risk Management](../plans/software_risk_management.xlsx) with a sequential Hazard ID following the format SAF-XXX where XXX denotes a three digit unique ID that follows the last documented ID, starting from 001.

2. **Document Sequences of Events**

    If any hazardous situations were identified in the previous step, then add any sequences of events that may lead to those in the same record written in hazardous situations in [Risk Management](../plans/software_risk_management.xlsx). Note that although IEC 62304 distinguishes between sequences of events leading to a hazardous situation and software causes of a hazardous situation, we consider the "cause" to mean the penultimate event in the sequence and hence don't distinguish them in our documentation.

    When enumerating sequences of events leading to hazardous situations, consider:

    - incorrect or incomplete specifications of functionality [[62304:7.1.2.a]]
    - software defects in the code being added or modified [[62304:7.1.2.b]]
    - failures or unexpected results from new or existing dependencies [[62304:7.1.2.c]]
    - hardware failures [[62304:7.1.2.d]]
    - other software defects that could result in unpredictable software operation [[62304:7.1.2.d]]
    - reasonably foreseeable misuse [[62304:7.1.2.e]]
    - unreliable network connections
    - cybersecurity vulnerabilities
    - interference with existing risk control measures documented in [Risk Management](../plans/software_risk_management.xlsx) [[62304:7.4.2]]

    Only be as detailed as is useful for improving the software.

**Outputs:** Updates to [Risk Management](../plans/software_risk_management.xlsx)

**Verified by:** Another engineer

**Verification tasks:**

1. **Review Completeness**

    Consider whether all relevant sequences of events were captured. Also, review that the granularity of the sequences of events is appropriate. Review if all columns are filled appropriately for the hazard documented.

2. **Review Traceability**

    Confirm that the software item, sequences of events, hazardous situation, and risk control measures can be traced together [[62304:7.3.3.a, 62304:7.3.3.b, 62304:7.3.3.c, and 62304:7.3.3.d]].