# LayerLogic — Software Development Life Cycle (SDLC)

> **The single source of truth for how LayerLogic builds, tests, and releases software.**

This wiki defines the complete Software Development Life Cycle (SDLC) for all LayerLogic projects. It is designed to ensure **quality**, **traceability**, **regulatory compliance** (IEC 62304 / FDA guidance), and **team efficiency** across every phase of development.

---

## 📖 Table of Contents

| Section                                     | Description                                            |
| ------------------------------------------- | ------------------------------------------------------ |
| [SDLC Overview](#sdlc-overview)             | High-level process flow for the entire lifecycle       |
| [Project Activities](#1-project-activities) | One-time setup activities when starting a new project  |
| [Sprint Activities](#2-sprint-activities)   | Recurring activities within each sprint cycle          |
| [Issue Activities](#3-issue-activities)     | Day-to-day engineering activities per change request   |
| [Release Activities](#4-release-activities) | Activities performed when preparing a release          |
| [Plans & Templates](#5-plans--templates)    | Testing plans, risk management, and document templates |
| [Data & Definitions](#6-data--definitions)  | Glossary, acronyms, and shared data definitions        |
| [GitHub Templates](#7-github-templates)     | Issue and PR templates for standardized workflows      |
| [Onboarding](#8-onboarding)                 | New engineer onboarding plan and checklists            |
| [Contributing](#contributing)               | How to contribute to this wiki                         |

---

## SDLC Overview

LayerLogic follows an **Agile SDLC** with built-in regulatory traceability. The lifecycle is organised into four layers of activities:

```
┌─────────────────────────────────────────────────────────────────┐
│                     PROJECT ACTIVITIES                          │
│  (One-time setup: planning, requirements, architecture, risk)  │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│   ┌─────────────────────────────────────────────────────────┐   │
│   │                  RELEASE CYCLE                          │   │
│   │  Planning → Development Sprints → Testing → Release     │   │
│   │                                                         │   │
│   │   ┌─────────────────────────────────────────────────┐   │   │
│   │   │              SPRINT CYCLE (2 weeks)             │   │   │
│   │   │  Planning → Issue Work → Demo → Retrospective   │   │   │
│   │   │                                                 │   │   │
│   │   │   ┌─────────────────────────────────────────┐   │   │   │
│   │   │   │          ISSUE ACTIVITIES               │   │   │   │
│   │   │   │  Requirements → Design → Risk →         │   │   │   │
│   │   │   │  Implementation → Testing →             │   │   │   │
│   │   │   │  Pull Request → Review                  │   │   │   │
│   │   │   └─────────────────────────────────────────┘   │   │   │
│   │   │                                                 │   │   │
│   │   └─────────────────────────────────────────────────┘   │   │
│   │                                                         │   │
│   │  Final Verification → System Testing → Release Record   │   │
│   └─────────────────────────────────────────────────────────┘   │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

### Activity Flow (Issue Level)

The typical flow for a single change request/issue:

```
Change Request Created
        │
        ▼
 Requirements Analysis ──→ Design Specifications
        │                          │
        ▼                          ▼
   Risk Analysis              Implementation
        │                          │
        ▼                          ▼
  Writing Tests ◄──────── Construction
        │
        ▼
  Pull Request Created
        │
        ▼
  Pull Request Reviewed
        │
        ▼
  Merged to Main
```

---

## 1. Project Activities

> _Performed once at the start of each new project._

| #   | Activity                                                                             | Description                                                   | Owner                           |
| --- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------- | ------------------------------- |
| 1   | [Planning & Setup](project_activities/planning_and_setup.md)                         | Repository setup, tooling, labels, and process configuration  | Project Lead                    |
| 2   | [Initial Requirements Analysis](project_activities/initial_requirements_analysis.md) | Enumerate major software and system requirements              | Project Lead + Product Owner    |
| 3   | [Initial Architecture Design](project_activities/initial_architecture_design.md)     | Define the software system architecture and core technologies | Project Lead + Engineering Team |
| 4   | [Initial Risk Analysis](project_activities/risk_analysis.md)                         | Identify initial hazards and hazardous situations             | Engineering Team + Project Lead |
| 5   | [Creating Change Requests](project_activities/creating_change_request.md)            | How to record chunks of development work as GitHub issues     | Anyone                          |

---

## 2. Sprint Activities

> _Performed on a recurring cadence (typically every 2 weeks)._

| #   | Activity                                                | Description                                    | Owner            |
| --- | ------------------------------------------------------- | ---------------------------------------------- | ---------------- |
| 1   | [Sprint Planning](sprint_activities/sprint_planning.md) | Demos, assignments, and process retrospectives | Engineering Team |

---

## 3. Issue Activities

> _Performed for each change request / issue during a sprint._

| #   | Activity                                                               | Description                                     | Owner             |
| --- | ---------------------------------------------------------------------- | ----------------------------------------------- | ----------------- |
| 1   | [Requirements Analysis](issue_activities/requirements_analysis.md)     | Refine and document software requirements       | Assigned Engineer |
| 2   | [Design Specifications](issue_activities/design_specifications.md)     | Architectural design and documentation          | Assigned Engineer |
| 3   | [Risk Analysis](issue_activities/risk_analysis.md)                     | Identify and document hazardous situations      | Assigned Engineer |
| 4   | [Implementation](issue_activities/implementation.md)                   | Code construction, combining all sub-activities | Assigned Engineer |
| 5   | [Writing Tests](issue_activities/writing_tests.md)                     | Unit, integration, and manual test creation     | Assigned Engineer |
| 6   | [Adding Dependencies](issue_activities/adding_dependencies.md)         | Evaluate and incorporate new SOUP/dependencies  | Assigned Engineer |
| 7   | [Creating Pull Requests](issue_activities/creating_pull_requests.md)   | Branch, commit, and merge workflow              | Assigned Engineer |
| 8   | [Reviewing Pull Requests](issue_activities/reviewing_pull_requests.md) | Code review and verification process            | Reviewer          |
| 9   | [Problem Resolution](issue_activities/problem_resolution.md)           | Investigate, fix, or defer reported problems    | Assigned Engineer |

---

## 4. Release Activities

> _Performed when preparing a software release._

| #   | Activity                                                                 | Description                                                 | Owner        |
| --- | ------------------------------------------------------------------------ | ----------------------------------------------------------- | ------------ |
| 1   | [Release Planning](release_activities/planning.md)                       | Version selection, dependency review, change request triage | Project Lead |
| 2   | [Software System Testing](release_activities/software_system_testing.md) | Unit, integration, and manual system tests                  | Engineer     |
| 3   | [Final Verification](release_activities/final_verification.md)           | Comprehensive release checklist                             | Project Lead |
| 4   | [Release Record](release_activities/release_record.md)                   | Template for documenting the release                        | Project Lead |
| 5   | [Test Record](release_activities/test_record.md)                         | Template for documenting test results                       | Engineer     |

---

## 5. Plans & Templates

| Document                                                        | Description                                                         |
| --------------------------------------------------------------- | ------------------------------------------------------------------- |
| [Testing Plan](plans/testing_plan.md)                           | Test strategy, types, coverage requirements, and pass/fail criteria |
| [Software Risk Management](plans/software_risk_management.xlsx) | Risk register with hazards, sequences of events, and mitigations    |

---

## 6. Data & Definitions

| Document                                      | Description                                |
| --------------------------------------------- | ------------------------------------------ |
| [Definitions & Glossary](data/definitions.md) | Key terms, acronyms, and shared vocabulary |

---

## 7. GitHub Templates

| Template                                                       | Description                                 |
| -------------------------------------------------------------- | ------------------------------------------- |
| [Bug Report](.github/ISSUE_TEMPLATE/bug_report.yaml)           | Structured template for reporting bugs      |
| [Feature Request](.github/ISSUE_TEMPLATE/feature_request.yaml) | Structured template for requesting features |
| [Change Request](.github/ISSUE_TEMPLATE/change_request.yaml)   | Structured template for change requests     |
| [Pull Request Template](.github/pull_request_template.md)      | Standardised PR description format          |

---

## 8. Onboarding

> _For new engineers joining LayerLogic._

| Document                                                      | Description                                                                 |
| ------------------------------------------------------------- | --------------------------------------------------------------------------- |
| [Engineer Onboarding Plan](onboarding/engineer_onboarding.md) | 5-day onboarding guide with daily goals, setup instructions, and checklists |

---

## Contributing

### Making Changes to This Wiki

All changes to this wiki must follow the same SDLC process:

1. **Create a change request** (GitHub issue) describing the documentation change
2. **Create a branch** named `<issue-number>-short-description`
3. **Make your changes** and commit with the issue reference (e.g., `Issue #42`)
4. **Create a pull request** and assign a reviewer
5. **Merge** once approved

### Document Standards

- All activity documents must include: **Trigger**, **Performed by**, **Inputs**, **Tasks**, **Outputs**, **Verified by**, and **Verification tasks**
- Use IEC 62304 clause references in double brackets: `[[62304:X.X.X]]`
- Cross-reference other activities using relative markdown links
- Keep language clear, concise, and actionable

---

## Regulatory References

This SDLC is designed to comply with:

- **IEC 62304** — Medical device software lifecycle processes
- **FDA Software Guidance** — General Principles of Software Validation

All clause references are noted inline using the format `[[62304:X.X.X]]` or `[[FDA-SW:section]]`.

---

_Last updated: 2026-02-14_
