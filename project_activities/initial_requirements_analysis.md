## Project — Initial Requirements Analysis

> How to enumerate major software and system requirements at the start of a project.

---

**Trigger:** Start of a new project

**Performed by:** Project Lead with the Product Owner

**Inputs:** User needs, system requirements, and risk control measures

---

### Tasks

#### 1. Definitions

Add definitions for key terms and acronyms to the [Definitions & Glossary](../data/definitions.md) document. Standard and concise definitions can clarify team communication significantly, much like good data abstractions can simplify a software project.

#### 2. Software Requirements

To the extent possible, major software requirements should be enumerated at the start of the project [[62304:5.2.1]].

Write requirements following the [Requirements Analysis Activity](../issue_activities/requirements_analysis.md).

Software requirements are often categorised as one of the following types [[62304:5.2.2, 62304:5.2.3]]:

**a. Functional and Capability Requirements** [[62304:5.2.2.a]]

- Performance (e.g., purpose of the software, timing requirements)
- Physical characteristics (e.g., code language, platform, operating system)
- Computing environment (e.g., hardware, memory size, processing unit, time zone, network infrastructure) under which the software is to perform
- Need for compatibility with upgrades or multiple SOUP or other device versions

**b. Software System Inputs and Outputs** [[62304:5.2.2.b]]

- Data characteristics (e.g., numerical, alpha-numeric, format)
- Ranges, limits, and defaults

**c. Interfaces Between the Software System and Other Systems** [[62304:5.2.2.c]]

- Communication protocols
- API contracts
- Hardware interfaces

**d. Security Requirements** [[62304:5.2.2.e]]

- Compromise of sensitive information
- Authentication and authorisation
- Audit trail
- Communication integrity
- Data encryption at rest and in transit

**e. Data Definitions and Database Requirements** [[62304:5.2.2.g]]

- Data models and schemas
- Data retention policies
- Backup and recovery requirements

**f. Requirements Related to Methods of Operation and Maintenance** [[62304:5.2.2.i]]

- Deployment procedures
- Monitoring and alerting
- Logging requirements

**g. Regulatory Requirements** [[62304:5.2.2.l]]

- Applicable standards and guidelines
- Certification requirements
- Reporting obligations

---

**Outputs:** Draft SRS (Software Requirements Specification)

**Verified by:** See [Requirements Analysis](../issue_activities/requirements_analysis.md) verification tasks

**Verification tasks:** See [Requirements Analysis](../issue_activities/requirements_analysis.md) verification tasks
