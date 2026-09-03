# RFC: [Architectural or Feature Change Name]

* **RFC ID:** RFC-[0000]
* **Status:** [Draft | Under Review | Approved | Rejected | Implemented | Deferred | Withdrawn | Superseded by RFC-XXXX]
* **Author(s):** [Author Name(s)] <[Author Email(s)]>
* **Decider(s):** [Name/Role of Reviewers/Maintainers]
* **Created:** YYYY-MM-DD
* **Last Updated:** YYYY-MM-DD
* **Target Release:** [vX.Y.Z | N/A]

---

## Table of Contents

- [Summary](#summary)
- [Motivation & Problem Statement](#motivation--problem-statement)
- [Detailed Design](#detailed-design)
- [Drawbacks & Trade-offs](#drawbacks--trade-offs)
- [Rationale & Alternatives](#rationale--alternatives)
- [Unresolved Questions](#unresolved-questions)
- [Future Possibilities](#future-possibilities)

---

## Summary

A concise, one-paragraph explanation of the proposed change. Describe what is being built or changed
without diving deep into implementation details.

---

## Motivation & Problem Statement

Explain why this change is necessary:

* What core problem or limitation does this proposal address?
* What specific use cases does this support?
* What is the expected value or outcome upon completion?

If this RFC relates to existing issues or discussions, link them here.

---

## Detailed Design

This is the primary section of the RFC. Explain the solution in sufficient detail so that an
engineer familiar with the codebase can understand and implement it.

### Architecture & Components

Describe the structural changes, data flows, or new system modules introduced. Include diagrams or
plain text ASCII flows here if applicable.

### API / Interface Changes

Detail any new, modified, or deprecated interfaces, schemas, parameters, or configurations:

* **Breaking Changes:** [Yes/No - List any breaking API or behavior changes]
* **Data Migration:** [Describe database schema or persistent state changes, if applicable]

### Implementation Strategy

Outline the implementation phases, dependencies, or rollout steps required.

---

## Drawbacks & Trade-offs

Be explicit about the costs and downsides of this proposal:

* What complexity is added to the codebase or operational setup?
* What is the impact on build time, runtime performance, or memory usage?
* What edge cases or maintenance burdens does this create?

---

## Rationale & Alternatives

Explain why this approach was chosen over other possible designs:

1. **Alternative A ([Approach Name]):** Describe the primary alternative approach considered and why
   it was passed over.
2. **Alternative B (Do Nothing):** What is the impact of keeping the current behavior without any
   changes?
3. **Alternative X ([Custom Approach Name]):** Describe any additional potential approach and why it
   was passed over.

Mention any abandoned ideas or previous experiments related to this effort.

---

## Unresolved Questions

List open items or decisions that still need discussion before finalizing this RFC:

- [ ] Question 1: Describe open architectural or implementation detail
- [ ] Question 2: Describe potential risk needing benchmark or testing
- [ ] Question X: Describe any additional open question, risk, or validation needed

---

## Future Possibilities

Briefly describe potential future additions or extensions that build upon this work, but are out of
scope for this specific proposal.
