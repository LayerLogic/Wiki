## Issue - Design Specifications

**Trigger:** Software items are added, removed, or their architecture is modified

**Performed by:** Engineer implementing, or planning for, the change

**Inputs:** The existing architecture, risk analysis, and requirements

**Tasks:**

1. **Determine Architectural Design**

    Determine the architectural changes needed (adding/removing) to meet the new requirements. Keep in mind the existing architecture and risks associated with the change.

2. **Evaluation Need for Documentation**

    Is it necessary to document anything? Typically the high-level "why" questions are the most important to document.

3. **Update the Architectural Diagrams**

    Prefer block diagrams and flow charts to textual descriptions and include these diagrams in the project's storage. Indicate which software items are SOUP.

4. **Add a Textual Section to the Project's Storage**

    Textual descriptions are often necessary in addition to architectural diagrams. These detailed designs should be stored as closely as possible to their corresponding source files.

    Each new software item must include a detailed design [[62304:5.4.2]]. As appropriate, write out function signatures for the essential procedures, functions, classes, interfaces between software items and external components (hardware or software) as appropriate, and/or modules involved with the change request.

5. **User Interface Design**

    If you're making large changes to the user interface, you need to first create user interface mockups. Don't begin implementing the changes until the product owner has approved the user interface mockups.

    If you're modifying an existing UI, consider updating the mockup first.

    Include the UI mockups in the project's storage as appropriate.

**Outputs:** Updates to the project's storage

**Verified by:** Another engineer

**Verification tasks:**

1. **Evaluate SDS**

    Ensure software architecture documented:

    - is not more complicated than it needs to be to meet the requirements
    - is free from contradiction with other architectures [[62304:5.4.4.b]].
    - implements system and software requirements [[62304:5.4.4.a 62304:5.3.6.a]].
    - is able to support interfaces between software items and between software items and hardware [[62304:5.3.6.b]].