## Issue — Implementation

> The core engineering activity: requirements, design, risk, testing, and code construction.

---

**Trigger:** Working on an assigned change request during a sprint

**Performed by:** The engineer assigned to the change request

**Inputs:** The change request (GitHub issue) and the system architecture (SDS)

---

### Tasks

> **Note:** These tasks do not need to be performed in strict order. Often, gaps in requirements won't become clear until you begin coding. We recommend writing some tests first (or planning how to write them), since doing so often leads to better designs.

#### 1. Requirements Gathering

Perform the [Requirements Analysis](./requirements_analysis.md) activity as appropriate.

If the requirements are very uncertain, have the product owner review them before spending too much time on design or construction.

#### 2. Design Specifications

Perform the [Design Specifications](./design_specifications.md) activity as appropriate.

If you're new to the project or uncertain about the design, consider having the project lead or another engineer review your design up-front before writing code.

#### 3. Risk Analysis

Perform the [Risk Analysis](./risk_analysis.md) activity as appropriate.

#### 4. Testing

Perform the [Writing Tests](./writing_tests.md) activity as appropriate.

#### 5. Construction

During code construction, as appropriate:

- [ ] Follow the development standards and methods specified in the project's software plan
- [ ] Consider whether your changes could cause software items to be refactored or reused [[62304:6.2.3]]. Create `TODO` comments or change requests as appropriate.
- [ ] Consider whether any external systems that the software interfaces with may be affected [[62304:6.2.3]]
- [ ] If the software has been released, consider whether data on existing systems needs to be migrated
- [ ] Ensure code is clean, readable, and well-commented where non-obvious logic exists
- [ ] Run linters and static analysis tools before committing

---

**Outputs:** Code and documentation changes

**Verified by:** Another engineer (via pull request review)

### Verification Tasks

1. **Requirements** — Complete verification tasks in the [Requirements Analysis](./requirements_analysis.md) activity, as appropriate.
2. **Design Specifications** — Complete verification tasks in the [Design Specifications](./design_specifications.md) activity, as appropriate.
3. **Risk Analysis** — Complete verification tasks in the [Risk Analysis](./risk_analysis.md) activity, as appropriate.
4. **Testing** — Complete verification tasks in the [Writing Tests](./writing_tests.md) activity, as appropriate.
5. **Construction** — Ensure the code follows the project's software standards, including:
   - [ ] Coding style and conventions
   - [ ] No unnecessary dependencies introduced
   - [ ] No commented-out code or debug statements left in
   - [ ] Error handling is appropriate

---

**Regulatory Notes:** This activity addresses [[62304:5.5.1]].
