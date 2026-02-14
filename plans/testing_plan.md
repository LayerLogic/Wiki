# Testing Plan

> Defines the test strategy, test types, coverage requirements, and pass/fail criteria for all LayerLogic projects.

---

## 1. Purpose

This document establishes the testing strategy for software developed by LayerLogic. It ensures that all software requirements are verified, risks are mitigated, and releases meet quality standards before deployment [[62304:5.5, 62304:5.6, 62304:5.7]].

---

## 2. Test Strategy Overview

LayerLogic employs a **multi-layered testing strategy** that combines automated and manual testing:

```
┌──────────────────────────────────────┐
│          Manual System Tests         │  ← End-to-end user-facing validation
├──────────────────────────────────────┤
│         Integration Tests            │  ← Component interaction verification
├──────────────────────────────────────┤
│            Unit Tests                │  ← Individual module/function verification
└──────────────────────────────────────┘
```

Testing is performed **continuously** during development (via CI/CD) and **formally** before each release (via the [Software System Testing](../release_activities/software_system_testing.md) activity).

---

## 3. Test Types

### 3.1 Unit Tests

| Attribute           | Details                                                                         |
| ------------------- | ------------------------------------------------------------------------------- |
| **Scope**           | Individual functions, methods, classes, or modules                              |
| **Performed by**    | Engineer implementing the change                                                |
| **Automation**      | Fully automated; executed on every commit via CI                                |
| **Framework**       | Project-specific (e.g., Jest, PyTest, xUnit)                                    |
| **Coverage target** | ≥ 80% line coverage for safety-critical modules; ≥ 60% for non-critical modules |

**Purpose:** Verify that each software unit performs its intended function correctly in isolation [[62304:5.5.1, 62304:5.5.2]].

### 3.2 Integration Tests

| Attribute           | Details                                                               |
| ------------------- | --------------------------------------------------------------------- |
| **Scope**           | Interactions between software items, modules, and external interfaces |
| **Performed by**    | Engineer implementing the change                                      |
| **Automation**      | Automated where possible; executed on every pull request via CI       |
| **Framework**       | Project-specific                                                      |
| **Coverage target** | All inter-module interfaces and data flows must be tested             |

**Purpose:** Verify that software items work correctly together and that interfaces between components behave as specified [[62304:5.6.1, 62304:5.6.5]].

### 3.3 Manual System Tests

| Attribute        | Details                                                                                       |
| ---------------- | --------------------------------------------------------------------------------------------- |
| **Scope**        | End-to-end user workflows, UI interactions, and real-world scenarios                          |
| **Performed by** | Engineer or QA (during release verification)                                                  |
| **Automation**   | Manual execution; results recorded in the [Test Record](../release_activities/test_record.md) |
| **Environment**  | Staging environment that mirrors production as closely as possible                            |

**Purpose:** Validate that the complete software system meets user needs and system requirements in a realistic environment [[62304:5.7.1]].

### 3.4 Regression Tests

| Attribute        | Details                                                     |
| ---------------- | ----------------------------------------------------------- |
| **Scope**        | Previously passing test cases re-executed after changes     |
| **Performed by** | Automated via CI; manual regression during releases         |
| **Purpose**      | Ensure that new changes do not break existing functionality |

---

## 4. Test Coverage Requirements

### 4.1 Requirements Traceability

Every software requirement **must** be covered by at least one test case [[62304:5.7.4.a]]. The traceability is documented in the [Test Record](../release_activities/test_record.md) using the `Requirement IDs` column.

### 4.2 Risk-Based Coverage

Software items associated with higher-risk hazardous situations (as documented in the [Risk Management file](./software_risk_management.xlsx)) require **more thorough** test coverage, including:

- Multiple test cases covering nominal, boundary, and error conditions
- Integration tests verifying risk control measures
- Manual tests validating user-facing safety features

---

## 5. Test Environment

### 5.1 Automated Test Environment

- Tests run in the CI/CD pipeline on each commit and pull request
- The CI environment must be documented (OS, runtime versions, dependencies)
- Tests must pass before a pull request can be merged

### 5.2 Manual Test Environment

- A staging environment must be provisioned for each release
- The staging environment must mirror production as closely as possible
- All environment details must be recorded in the [Test Record](../release_activities/test_record.md) [[62304:5.6.7.b, 62304:5.7.5.b]]

---

## 6. Pass/Fail Criteria

### 6.1 For Pull Requests

A pull request passes if:

- [ ] All automated unit tests pass
- [ ] All automated integration tests pass
- [ ] No new lint or static analysis warnings are introduced
- [ ] Code review is approved by the designated reviewer

### 6.2 For Releases

A release passes if:

- [ ] All automated unit tests pass in a clean environment
- [ ] All automated integration tests pass in a clean environment
- [ ] All manual system tests pass (as documented in the Test Record)
- [ ] All software requirements are traceable to at least one passing test
- [ ] No unresolved problem reports that result in unacceptable risk [[62304:5.8.3]]
- [ ] The test record is complete and signed off

### 6.3 Handling Test Failures

- Any test failure discovered during release testing **must** be recorded as a problem report [[62304:5.6.8]]
- If a fix is implemented, all affected tests **must** be re-run [[62304:5.7.3.a]]
- If only a subset of tests is re-run, a regression analysis must justify the decision in the test record

---

## 7. Testing Tools

Document the testing tools used for each project in the project's SDS. Common tools include:

| Category                        | Examples                          |
| ------------------------------- | --------------------------------- |
| **Unit test frameworks**        | Jest, PyTest, xUnit, Go testing   |
| **Integration test frameworks** | Supertest, Playwright, Cypress    |
| **Static analysis**             | ESLint, SonarQube, Pylint         |
| **CI/CD platforms**             | GitHub Actions, GitLab CI         |
| **Code coverage**               | Istanbul/nyc, coverage.py, JaCoCo |

---

## 8. Responsibilities

| Role              | Responsibility                                                  |
| ----------------- | --------------------------------------------------------------- |
| **Engineer**      | Write and maintain unit and integration tests for their changes |
| **Reviewer**      | Verify test completeness and utility during PR review           |
| **Project Lead**  | Ensure testing plan is followed; oversee release testing        |
| **Product Owner** | Validate that acceptance criteria reflect user needs            |

---

_This testing plan should be reviewed and updated at the start of each new project and whenever the testing strategy changes [[62304:5.1.2]]._
