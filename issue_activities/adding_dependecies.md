**Trigger:** Incorporating a new dependency, or SOUP Software Item, into the software

**Performed by:** Engineer adding the dependency

**Inputs:** Details regarding the dependency

**Tasks:**

1. **Evaluation**

   Most software dependencies introduce risks. Before incorporating new dependencies, consider the following questions:

   - Is the dependency strictly necessary? How much effort would it take to implement the provided functionality?
   - How widely used is the SOUP? Popular libraries tend to have fewer defects, better documentation, and longer lifetimes. Consider package download counts, issue tracker traffic, and GitHub stars, etc.
   - Is the library maintained? Consider the git commit frequency and the number of maintainers.
   - What is the project's license? Be sure it's compatible with the business needs.

2. **Update Architectural Diagram**

   Incorporate the new SOUP item into the SDS Documentation as appropriate. The benefit to engineers, especially new engineers, should be balanced with the cost of maintaining the diagrams and the risks associated with outdated diagrams. See the [Project - Architectural Design](#project---architectural-design) for details.

**Outputs:** Updated architecture diagram

**Verified by:** Another engineer

**Verification tasks:**

1. **Completeness**

   Review the updated architecture changes. Are they sufficiently complete?

2. **Formatting**
   Review the updated architecture changes. Are they formatted correctly?
