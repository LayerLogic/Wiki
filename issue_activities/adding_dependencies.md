## Issue — Adding Dependencies

> How to evaluate and incorporate new third-party dependencies (SOUP Software Items) into a project.

---

**Trigger:** Incorporating a new dependency, or SOUP Software Item, into the software

**Performed by:** Engineer adding the dependency

**Inputs:** Details regarding the dependency (name, version, license, purpose)

---

### Tasks

#### 1. Evaluation

Most software dependencies introduce risks. Before incorporating new dependencies, evaluate the following:

- [ ] **Necessity** — Is the dependency strictly necessary? How much effort would it take to implement the provided functionality in-house?
- [ ] **Adoption** — How widely used is the SOUP? Popular libraries tend to have fewer defects, better documentation, and longer lifetimes. Consider package download counts, issue tracker traffic, and GitHub stars.
- [ ] **Maintenance** — Is the library actively maintained? Consider git commit frequency, the number of maintainers, and the age of the most recent release.
- [ ] **License** — What is the project's license? Confirm it is compatible with LayerLogic's business needs and any regulatory requirements.
- [ ] **Security** — Does the dependency have known vulnerabilities? Check databases such as [Snyk](https://snyk.io), [npm audit](https://docs.npmjs.com/cli/v10/commands/npm-audit), or [OWASP Dependency-Check](https://owasp.org/www-project-dependency-check/).

#### 2. Document the Dependency

Record the following information in the project's SDS:

| Field          | Description                                                   |
| -------------- | ------------------------------------------------------------- |
| **Name**       | The dependency name                                           |
| **Version**    | The pinned version being used                                 |
| **License**    | The dependency's license type                                 |
| **Purpose**    | Why the dependency is being used                              |
| **Risk level** | Low / Medium / High — based on criticality to safety features |

#### 3. Update Architectural Diagram

Incorporate the new SOUP item into the SDS architectural diagrams as appropriate. The benefit to engineers, especially new engineers, should be balanced with the cost of maintaining the diagrams and the risks associated with outdated diagrams. See the [Initial Architecture Design](../project_activities/initial_architecture_design.md) for details.

---

**Outputs:** Updated SDS with dependency documentation and architecture diagram

**Verified by:** Another engineer

### Verification Tasks

1. **Evaluation Review** — Confirm the dependency evaluation criteria above were considered and documented.
2. **Completeness** — Review the updated architecture changes. Are they sufficiently complete?
3. **Formatting** — Review the updated architecture changes. Are they formatted correctly?
