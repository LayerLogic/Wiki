# Definitions & Glossary

> Standard definitions and acronyms used across all LayerLogic documentation and projects.

---

## Key Terms

| Term                                          | Definition                                                                                                                                                                                                                                                |
| --------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Change Request**                            | A documented request for a modification to the software. In LayerLogic's workflow, change requests are tracked as GitHub issues and must be approved before work begins. [[62304:8.2.1]]                                                                  |
| **Hazardous Situation**                       | A circumstance in which a person, property, or environment is exposed to one or more hazards. Hazardous situations are documented in the Risk Management file.                                                                                            |
| **Problem Report**                            | A record of a defect, anomaly, or unexpected behaviour discovered during development, testing, or post-release. In LayerLogic's workflow, a problem report is a GitHub issue tagged with the `bug` label. [[62304:9.1]]                                   |
| **Product Owner**                             | The individual responsible for defining product requirements, priorities, and acceptance criteria. The product owner validates that implemented features meet user needs.                                                                                 |
| **Project Lead**                              | The individual responsible for the overall technical direction, process compliance, and release management of a project.                                                                                                                                  |
| **Pull Request (PR)**                         | A request to merge a set of code changes from a feature branch into the main branch. PRs are the primary mechanism for code review and verification.                                                                                                      |
| **Release**                                   | A version of the software that is made available for use outside of the development team. Each release has a unique version number and associated documentation.                                                                                          |
| **Risk Control Measure**                      | An action or design decision implemented to reduce the risk associated with a hazardous situation to an acceptable level.                                                                                                                                 |
| **Software Item**                             | Any identifiable part of the software system — this can be a source file, module, library, class, function, or configuration file. [[62304:3.31]]                                                                                                         |
| **Software System**                           | The integrated collection of software items that together form the complete software product. [[62304:3.35]]                                                                                                                                              |
| **SOUP (Software of Unknown Provenance)**     | Software that is already developed and generally available but was not developed for the purpose of being incorporated into the medical device. Examples include open-source libraries, third-party SDKs, and operating system components. [[62304:3.29]] |
| **Sprint**                                    | A fixed-duration development iteration (typically 2 weeks) during which the team works on a set of assigned change requests.                                                                                                                              |
| **SDS (Software Design Specification)**       | A document describing the software system's architecture, interfaces, and detailed designs. [[62304:5.4]]                                                                                                                                                 |
| **SRS (Software Requirements Specification)** | A document enumerating all software requirements, traceable to system requirements and test cases. [[62304:5.2]]                                                                                                                                          |
| **Traceability**                              | The ability to link requirements → design → implementation → tests → risk controls so that every item can be traced through the lifecycle.                                                                                                                |
| **Verification**                              | Confirmation through examination and provision of objective evidence that specified requirements have been fulfilled. [[62304:3.38]]                                                                                                                      |
| **Validation**                                | Confirmation through examination and provision of objective evidence that the particular requirements for a specific intended use can be consistently fulfilled.                                                                                          |

---

## Acronyms

| Acronym   | Expansion                                      |
| --------- | ---------------------------------------------- |
| **CI/CD** | Continuous Integration / Continuous Deployment |
| **FDA**   | U.S. Food and Drug Administration              |
| **IEC**   | International Electrotechnical Commission      |
| **PR**    | Pull Request                                   |
| **QA**    | Quality Assurance                              |
| **SDS**   | Software Design Specification                  |
| **SDLC**  | Software Development Life Cycle                |
| **SOUP**  | Software of Unknown Provenance                 |
| **SRS**   | Software Requirements Specification            |
| **V&V**   | Verification and Validation                    |

---

## Regulatory Standards Referenced

| Standard                   | Title                                                               | Relevance                           |
| -------------------------- | ------------------------------------------------------------------- | ----------------------------------- |
| **IEC 62304:2006+A1:2015** | Medical device software — Software life cycle processes             | Primary software lifecycle standard |
| **IEC 14971:2019**         | Medical devices — Application of risk management to medical devices | Risk management framework           |
| **FDA Software Guidance**  | General Principles of Software Validation                           | FDA expectations for software V&V   |

---

## Document Identifier Conventions

| Prefix     | Document Type                    | Example       |
| ---------- | -------------------------------- | ------------- |
| `SRAR-`    | Software Release Activity Record | `SRAR-001`    |
| `TESTREC-` | Software Test Record             | `TESTREC-001` |
| `SAF-`     | Safety Hazard Identifier         | `SAF-001`     |
| `REQ-`     | Software Requirement             | `REQ-001`     |
| `SYS-`     | System Requirement               | `SYS-001`     |

---

_Add new definitions as they arise. Keep this list alphabetically sorted within each section._
