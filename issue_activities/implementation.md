## Issue - Implementation

**Trigger:** Working on an assigned change request during a sprint

**Performed by:** The engineer assigned to the change request

**Inputs:** The change request and the system architecture

**Tasks:**

Note that these tasks do not need to be performed in the order they're presented. Often gaps in the requirements may not be clear until you begin coding. We also recommend writing some tests first, or plan how you will write them, since doing so often leads to better designs.

1. **Requirements Gathering**

    Perform the [Issue - Requirements Analysis activity](./requirements_analysis.md) as appropriate.

    If the requirements are very uncertain, have the product owner review them before spending too much time on the design or construction.

2. **Design Specifications**

    Perform the [Issue - Design Specifications activity](./design_specifications.md) as appropriate.

    If you're new to the project or are uncertain about the design, consider having the project lead or another engineer review your design up-front.

3. **Risk Analysis**

    Perform the [Issue - Risk Analysis activity](./risk_analysis.md) as appropriate.

4. **Testing**

    Perform the [Issue - Writing Tests activity](./writing_tests.md) as appropriate.

5. **Construction**

    During code construction, as appropriate:

    - Follow development standards and methods specified earlier in this plan.
    - Consider whether your changes could cause software items to be refactored or reused [[62304:6.2.3]]. Create "TODO" statements or change requests as appropriate.
    - Consider whether any external systems that the software system interfaces with may be affected [[62304:6.2.3]].
    - If the software has been released, consider whether data on existing systems needs to be migrated.

**Outputs:** Code and documentation changes

**Verified by:** Another engineer

**Verification tasks:**

1. **Requirements**

    Complete verification tasks in the [Issue - Requirements Analysis activity](./requirements_analysis.md), as appropriate.

2. **Design Specifications**

    Complete verification tasks in the [Issue - Design Specification activity](./design_specifications.md), as appropriate.

3. **Risk Analysis**

    Complete verification tasks in the [Issue - Risk Analysis activity](./risk_analysis.md), as appropriate.

4. **Testing**

    Complete verification tasks in the [Issue - Writing Tests activity](./writing_tests.md), as appropriate.

5. **Construction**

    Ensure the code follows the project's software standards if any.

**Comments:**

[[:This activity addresses 62304:5.5.1]]
