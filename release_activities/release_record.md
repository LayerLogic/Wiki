---
id: SRAR-001
title: Software Release Activity Record
---

# Software Release Activity Record

## Purpose

The purpose of this document is to provide a record of the verification steps for the software release activity, as well as a record of how the release was built.

## Scope

This document applies to **[Project Name]** release **[version]**.

## Release Details

| Field               | Value                   |
| ------------------- | ----------------------- |
| **Release Version** | [e.g., v1.2.0]          |
| **Release Date**    | [YYYY-MM-DD]            |
| **Tagged Commit**   | [git commit hash]       |
| **Project Lead**    | [Name]                  |
| **Release Type**    | [Major / Minor / Patch] |

## Release Build Environment

> Record details about how the software release artefact was built. This should be detailed enough that another engineer could reproduce the artefact [[62304:5.8.5]].

| Component                       | Details                                |
| ------------------------------- | -------------------------------------- |
| **Build machine OS**            | [e.g., Ubuntu 22.04, macOS 14.2]       |
| **Runtime version**             | [e.g., Node.js 20.11.0, Python 3.12.1] |
| **Package manager**             | [e.g., npm 10.2.4, pip 23.3.2]         |
| **Build command**               | [e.g., `npm run build`]                |
| **Build artefact location**     | [e.g., GitHub Releases, S3 bucket URL] |
| **Artefact checksum (SHA-256)** | [hash value]                           |

## Release Verification

I, **[PROJECT LEAD'S NAME]**, verify the following:

- [ ] All of the planned change requests have been implemented and integrated
- [ ] The outputs of each activity are in a consistent state
- [ ] The unit tests adequately verify the software units
- [ ] The integration tests adequately verify the software system
- [ ] All software requirements have been tested or otherwise verified
- [ ] The software design specification (SDS) is accurate and up-to-date
- [ ] Integration and system testing has been completed after the last change request was integrated, and a test record has been written and linked below
- [ ] None of the known anomalies result in unacceptable risk
- [ ] The test results meet the required pass/fail criteria listed in the [Testing Plan](../plans/testing_plan.md)

## Linked Test Record

**Test Record:** [Link to test record for this release]

## Known Anomalies

> List any known issues that remain unresolved in this release, along with justification for why they are acceptable.

| Issue # | Description         | Severity          | Justification                        |
| ------- | ------------------- | ----------------- | ------------------------------------ |
| [#123]  | [Brief description] | [Low/Medium/High] | [Why this is acceptable for release] |

## Sign-Off

| Role              | Name   | Signature      | Date         |
| ----------------- | ------ | -------------- | ------------ |
| **Project Lead**  | [Name] | ******\_****** | [YYYY-MM-DD] |
| **Product Owner** | [Name] | ******\_****** | [YYYY-MM-DD] |

---

_This document should be compiled as a PDF and stored in the project file upon release._
