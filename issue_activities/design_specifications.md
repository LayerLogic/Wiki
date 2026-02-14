## Issue — Design Specifications

> How to determine, document, and verify architectural design changes.

---

**Trigger:** Software items are added, removed, or their architecture is modified

**Performed by:** Engineer implementing, or planning for, the change

**Inputs:** The existing architecture (SDS), risk analysis, and requirements (SRS)

---

### Tasks

#### 1. Determine Architectural Design

Determine the architectural changes needed (adding/removing software items) to meet the new requirements. Keep in mind the existing architecture and risks associated with the change.

#### 2. Evaluate Need for Documentation

Is it necessary to document anything? Consider:

- **Always document** the high-level "why" — the reasoning behind architectural decisions
- **Document when** adding new software items, external interfaces, or data flows
- **Skip documentation** for trivial internal refactors that don't change the architecture

#### 3. Update the Architectural Diagrams

- Prefer **block diagrams** and **flow charts** over textual descriptions
- Include diagrams in the project's SDS
- Indicate which software items are **SOUP**
- Use consistent diagram notation (e.g., C4 model, UML, or simple block diagrams)

#### 4. Add Textual Design Documentation

Textual descriptions are often necessary in addition to architectural diagrams. Detailed designs should be stored **as closely as possible to their corresponding source files** (e.g., in a `docs/` folder adjacent to the code, or as inline documentation).

Each new software item must include a detailed design [[62304:5.4.2]]. As appropriate, document:

- Function signatures for essential procedures and functions
- Class and module responsibilities
- Interfaces between software items and external components (hardware or software)
- Data flow descriptions
- State machines or sequence diagrams for complex interactions

#### 5. User Interface Design

If making **significant changes** to the user interface:

1. Create UI mockups **before** beginning implementation
2. Obtain product owner approval on the mockups
3. Include the UI mockups in the project's SDS

If modifying an existing UI, consider updating the mockup first to maintain design consistency.

---

**Outputs:** Updated SDS with architectural diagrams and/or textual design documentation

**Verified by:** Another engineer

### Verification Tasks

1. **Evaluate SDS** — Ensure the software architecture:
   - [ ] Is not more complicated than necessary to meet the requirements
   - [ ] Is free from contradiction with other architectural documentation [[62304:5.4.4.b]]
   - [ ] Implements system and software requirements [[62304:5.4.4.a, 62304:5.3.6.a]]
   - [ ] Supports interfaces between software items and between software items and hardware [[62304:5.3.6.b]]

2. **Evaluate Completeness** — Are all new/modified software items documented with sufficient detail?

3. **Evaluate Consistency** — Are the diagrams and textual descriptions consistent with each other and with the code?
