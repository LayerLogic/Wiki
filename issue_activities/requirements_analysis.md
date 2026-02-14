## Issue — Requirements Analysis

> How to refine, document, and verify software requirements for a change request.

---

**Trigger:** Adding or planning for new features with undocumented or changed requirements

**Performed by:** Engineer implementing, or planning for, the change

**Inputs:** Vague or partially specified requirements in the change request, or knowledge of user needs

---

### Tasks

#### 1. Evaluation

Is it necessary to write any new requirements [[62304:5.2.5]]?

Writing software requirements is an art and a science; if you're writing a set of requirements and it feels like a waste of time, some of them may not be necessary, or they may be too detailed. Focus on requirements that add clarity and enable verification.

#### 2. Write the Software Requirements

Add the requirements to the project's **SRS (Software Requirements Specification)** document, stored in the project repository.

> **Tip:** Each requirement should have a unique identifier following the convention `REQ-XXX` (see [Definitions](../data/definitions.md#document-identifier-conventions)).

**Software Requirements vs. System Requirements:**

The distinction between system requirements and software requirements can be challenging. System requirements describe the requirements of the entire system, including software and hardware. Software requirements must be traceable to all of the system requirements that they help fulfil. Software requirements are usually more detailed.

**Software Requirements vs. Design Specifications:**

| Software Requirements                      | Design Specifications                            |
| ------------------------------------------ | ------------------------------------------------ |
| Should **not** imply a specific solution   | Should describe one of possibly many solutions   |
| Must be **verifiable** (testable)          | Should be **detailed** enough for implementation |
| Should be **short** — ideally one sentence | May be longer and include diagrams               |

#### 3. Tie to System Requirements

If system requirements exist, each software requirement must be linked to one or more system requirements via the system-requirement IDs [[62304:5.1.1.c, 62304:5.1.3.a, 62304:5.1.3.b]].

If no matching system requirement exists, either:

- Add a new system requirement [[62304:5.2.5]], or
- Document the rationale for why the software requirement stands alone

---

**Outputs:** Updated SRS with new or modified requirements

**Verified by:** Product Owner

### Verification Tasks

#### 1. Content Correctness

The product owner (and ultimately the end-users) is best positioned to validate that the requirements are _correct_. This verification should occur during sprint planning meetings.

Review the change request and ensure that the documented requirements are consistent with your understanding.

#### 2. Formal Correctness

Review the documented requirements, ensuring they:

- [ ] Balance completeness with utility
- [ ] Don't contradict each other [[62304:5.2.6.b]]
- [ ] Have unambiguous descriptions [[62304:5.2.6.c]]
- [ ] Each has a unique identifier [[62304:5.2.6.e]]
- [ ] Are stated in terms that permit testing to determine whether criteria have been met [[62304:5.2.6.d]]

#### 3. System Requirements Traceability

- [ ] Ensure each software requirement traces back to a system-requirement ID (if they exist) [[62304:5.2.6.a, 62304:5.2.6.f]]
