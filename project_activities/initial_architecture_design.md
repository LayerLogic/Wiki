## Project — Initial Architecture Design

> How to establish the software system architecture and select core technologies at the start of a project.

---

**Trigger:** Start of a new project

**Performed by:** Project Lead with the engineering team

**Inputs:** Draft SRS, existing system architecture (if any)

---

### Tasks

#### 1. Document Software Items

Develop an initial software system architecture and document it in the SDS (Software Design Specification) [[62304:5.3.1]].

The SDS should describe:

- How the software system is divided into a hierarchy of software items [[62304:5.4.1]]
- The responsibilities of each major software item
- The interfaces between software items
- The interfaces between software items and external systems (hardware, APIs, etc.)

> **Guidance:** The level of granularity should be higher for higher-risk components. The initial architecture does not need to be complete since code construction can guide architectural decisions. However, investing significant time in the initial architecture reduces costly rework later.

Following the [Design Specifications](../issue_activities/design_specifications.md) activity, update the architectural diagrams and fill in parts of the SDS.

#### 2. Select Core Technologies

Following the [Adding Dependencies](../issue_activities/adding_dependencies.md) activity, evaluate and record details about the core technologies that will be used on the project:

| Technology                  | Details to Record                               |
| --------------------------- | ----------------------------------------------- |
| **Programming language(s)** | Language, version, and runtime                  |
| **Frameworks**              | Web framework, ORM, etc.                        |
| **Build tools**             | Compiler, bundler, package manager              |
| **Database**                | Type, version, hosting                          |
| **Infrastructure**          | Cloud provider, containerisation, orchestration |
| **SOUP / key libraries**    | Major third-party dependencies                  |

#### 3. Define Architecture Diagrams

Create the following diagrams (at minimum):

- [ ] **System context diagram** — shows the software system and its external interfaces
- [ ] **Component/container diagram** — shows the major software items and their relationships
- [ ] **Data flow diagram** — shows how data moves through the system (if applicable)

---

**Outputs:** Draft SDS with architecture diagrams and technology selections

**Verified by:** See [Design Specifications](../issue_activities/design_specifications.md) verification tasks

**Verification tasks:** See [Design Specifications](../issue_activities/design_specifications.md) verification tasks
