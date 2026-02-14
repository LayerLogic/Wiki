---
id: TESTREC-001
title: Software Test Record
---

# Software Test Record

## Purpose

The purpose of this document is to record the procedures followed to run the software unit, integration, and system tests, as well as the results of running these tests.

[[FDA-SW:vandv, FDA-SW:vandv-summary]]

## Scope

This document covers the software system within the **[Project Name]** product, release **[version]**.

## Verification

I, **[FULL DEVELOPER NAME]**, verify that the results recorded here are complete and accurate [[62304:9.8.g]].

**Tester:** [Name of the person who executed the tests — especially important for manual tests]

**Date of Testing:** [YYYY-MM-DD] [[62304:9.8.f]]

**Overall Result:** The tests [PASS / FAIL] our specified pass/fail criteria (see [Testing Plan](../plans/testing_plan.md)).

## Test Procedure and Environment

### Software Version

| Field                       | Value                                    |
| --------------------------- | ---------------------------------------- |
| **Git commit hash**         | [e.g., `abc1234def5678`] [[62304:9.8.c]] |
| **Git tag**                 | [e.g., `v1.2.0`]                         |
| **Branch**                  | [e.g., `main`]                           |
| **Working directory clean** | [Yes / No — must be Yes]                 |

### Environment Details [[62304:9.8.d]]

| Component            | Details                             |
| -------------------- | ----------------------------------- |
| **Operating System** | [e.g., Ubuntu 22.04 LTS]            |
| **Runtime**          | [e.g., Node.js 20.11.0]             |
| **Package manager**  | [e.g., npm 10.2.4]                  |
| **Database**         | [e.g., PostgreSQL 16.1]             |
| **Hardware**         | [e.g., MacBook Pro M3, 16GB RAM]    |
| **Network**          | [e.g., Local / VPN / Cloud staging] |

### Relevant Environment Variables

```bash
# List any non-secret environment variables that affect test execution
NODE_ENV=test
DATABASE_URL=postgres://localhost:5432/test_db
```

### Testing Tools [[62304:5.1.11, 62304:9.8.e]]

| Tool                 | Version        | Purpose                       |
| -------------------- | -------------- | ----------------------------- |
| [e.g., Jest]         | [e.g., 29.7.0] | Unit test runner              |
| [e.g., Playwright]   | [e.g., 1.41.0] | Integration / E2E test runner |
| [e.g., Istanbul/nyc] | [e.g., 15.1.0] | Code coverage                 |

### Test Execution Procedure

**Unit tests:**

```bash
# Document the exact commands used to run unit tests
npm run test:unit
```

[[FDA-SW:vandv-unit-protocol]]

**Integration tests:**

```bash
# Document the exact commands used to run integration tests
npm run test:integration
```

[[FDA-SW:vandv-integration-protocol]]

**Manual system tests:**

> Describe the staging environment setup and the procedure for running manual tests.

[Describe the staging environment and how manual tests were conducted]

[[FDA-SW:vandv-system-protocol]]

## Regression Analysis

[[FDA-SW:vandv-changes]]

> If the software is a modified version of a previously cleared/approved version, summarise the modifications compared with the previous version.

**Modifications summary:** [Describe changes from previous version, or "N/A — initial release"]

[[FDA-SW:vandv-regression-analysis]]

> If only a subset of tests was re-run after a fix, document the regression analysis here, explaining why the subset is sufficient.

**Regression analysis:** [Describe the analysis, or "N/A — all tests were run"]

## Test Results

[[These are the results of automated unit and integration testing as well as system testing — 62304:9.8.a]]

### Code Coverage Summary

| Metric                | Value         |
| --------------------- | ------------- |
| **Line coverage**     | [e.g., 87.3%] |
| **Branch coverage**   | [e.g., 72.1%] |
| **Function coverage** | [e.g., 91.5%] |

### Unit Tests [[FDA-SW:vandv-unit-report]]

| Test Name     | Test Status | Requirement IDs  | Notes                   |
| ------------- | ----------- | ---------------- | ----------------------- |
| [test_name_1] | ✅ Pass     | REQ-001, REQ-002 |                         |
| [test_name_2] | ✅ Pass     | REQ-003          |                         |
| [test_name_3] | ❌ Fail     | REQ-004          | See Problem Report #123 |

### Integration Tests [[FDA-SW:vandv-integration-report]]

| Test Name     | Test Status | Requirement IDs  | Notes |
| ------------- | ----------- | ---------------- | ----- |
| [test_name_1] | ✅ Pass     | REQ-005, REQ-006 |       |
| [test_name_2] | ✅ Pass     | REQ-007          |       |

### Manual System Tests [[FDA-SW:vandv-system-report]]

| Test Name         | Step                          | Test Status | Requirement IDs | Notes                             |
| ----------------- | ----------------------------- | ----------- | --------------- | --------------------------------- |
| [test_scenario_1] | Navigate to login page        | ✅ Pass     | REQ-010         |                                   |
| [test_scenario_1] | Enter valid credentials       | ✅ Pass     | REQ-011         |                                   |
| [test_scenario_1] | Verify dashboard loads        | ✅ Pass     | REQ-012         |                                   |
| [test_scenario_2] | Submit form with invalid data | ✅ Pass     | REQ-013         | Error message displayed correctly |

### Anomalies Encountered [[62304:9.8.b]]

| Problem Report # | Description         | Severity                   | Resolution                    |
| ---------------- | ------------------- | -------------------------- | ----------------------------- |
| [#123]           | [Brief description] | [Critical/High/Medium/Low] | [Fixed / Deferred / Accepted] |

---

## Sign-Off

| Role         | Name   | Signature      | Date         |
| ------------ | ------ | -------------- | ------------ |
| **Tester**   | [Name] | ******\_****** | [YYYY-MM-DD] |
| **Reviewer** | [Name] | ******\_****** | [YYYY-MM-DD] |

---

_It is acceptable for some tests to not trace to any particular requirements. However, all requirements must be covered by at least one test. If they are not, add tests before releasing._
