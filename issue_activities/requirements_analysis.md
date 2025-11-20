## Issue - Requirements Analysis

**Trigger:** Adding or planning for new features with undocumented or changed requirements

**Performed by:** Engineer implementing, or planning for, the change

**Inputs:** Vague or partially specified requirements in the change request or knowledge of the user needs

**Tasks:**

1. **Evaluation**

    Is it necessary to write any new requirements [[62304:5.2.5]]?

    Writing software requirements is an art and a science; if you're writing a set of requirements and it feels like a waste of time, some of them may not be necessary, or they may be too detailed.

2. **Write the Software Requirements**

    Add the requirements to {{workflow.software_requirements_location}}.

Software and System requirements:

    The distinction between system requirements and software requirements can be challenging. System requirements describe the requirements of the entire system, including software and hardware. Software requirements must be traceable to all of the system requirements that they help fulfill. Software requirements are usually more detailed.

Software and Design Specifications:

    The distinction between software requirements and design specifications can be challenging.

    Requirements should:

    - not imply solution
    - be verifiable
    - be short, ideally one sentence.

    Design specifications, on the other hand, should:

    - be one of, possibly, many solutions
    - be detailed.

3. **Tie to System Requirements**

    If existing, system requirements are stored in {{workflow.system_requirements_location}}. Each system requirement must have a unique identifier so that we can trace software requirements back to the system requirements they fulfill [[62304:5.1.3.a 62304:5.1.3.b]]. 
    
    Software requirements must be tied to one or more originating system requirements via the system-requirement ids [[62304:5.1.1.c]], or new system requirements should be added accordingly [[62304:5.2.5]].

**Outputs:** Updates to {{workflow.software_requirements_location}}

**Verified by:** Project owner

**Verification tasks:**

1. **Content Correctness**

    The product owner (and really the end-users) is best positioned to validate that the requirements are _correct_. This verification should occur during the weekly sprint planning meetings.

    It's worth reviewing the change request and ensuring that the requirements documented in {{workflow.software_requirements_location}} are consistent with your understanding.

1. **Formal Correctness**

    Review the documented requirements, ensuring they

    - balance completeness with utility
    - don't contradict each other [[62304:5.2.6.b]]
    - don't have unambiguous descriptions [[62304:5.2.6.c]]
    - each has a unique identifier [[62304:5.2.6.e]]
    - are stated in terms that permit the performance of tests to determine whether the test criteria have been met [[62304:5.2.6.d]].

2. **System Requirements Traceability**

    Ensure each software requirement traces back to a system-requirement id if they exist [[62304:5.2.6.a 62304:5.2.6.f]].
    