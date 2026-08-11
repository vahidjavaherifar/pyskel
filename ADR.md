# ADR-0000: [Short Title of the Decision]

* **Status:** [Proposed | Accepted | Rejected | Deprecated | Superseded by ADR-XXXX]
* **Date:** YYYY-MM-DD
* **Deciders:** [Names or Roles of People Involved]
* **Technical Story:** [Issue / PR / Ticket Number or Discussion Link]

---

## 1. Context & Problem Statement

Describe the technical, operational, or business situation that necessitates this decision. What
issue are we facing? What are the limitations or constraints of the current system? State the core
problem clearly without jumping to a premature solution.

---

## 2. Decision Drivers & Forces

Identify the critical priorities, quality attributes, and strict boundaries shaping this decision:

* **Primary Driver:** Describe the non-negotiable functional or technical goal driving this
  architecture change.
* **Secondary Drivers:** Describe supporting requirements such as maintainability, developer
  experience, or cost efficiency.
* **Constraints:** Define mandatory technical, security, legal, or infrastructural limitations that
  must be respected.

---

## 3. Considered Options

List all viable architectural patterns, frameworks, libraries, or design strategies evaluated for
this decision:

* **Option 1:** [Name of Option 1] — Short baseline description. 
* **Option 2:** [Name of Option 2] — Short baseline description. 
* **Option 3:** [Name of Option 3] — Short baseline description. 
* **Option X:** [Name of Option N] — Short baseline description. 

---

## 4. Decision Outcome & Summary Statement

### Selected Option
* **Chosen Option:** **[Option X]**

### Summary Statement (Y-Statement)
> In the context of **[Context / Problem]**,
> facing **[Decision Drivers / Constraints]**,
> we decided for **[Chosen Option]**,
> to achieve **[Primary Benefit]**,
> accepting **[Trade-off / Risk]**.

### Justification
Provide a direct explanation of why this option was chosen over the others based on the decision
drivers. Highlight the key technical advantage that made it the winner.

---

## 5. Option Comparison & Pros/Cons

### Option 1: [Name of Evaluated Option]
* **Positive:** Describe a major advantage, capability, or benefit offered by this option.
* **Negative:** Describe a major disadvantage, trade-off, or limitation of this option.
* **Rejection Reason:** State the decisive technical or business reason why this option was not
  selected.

### Option 2: [Name of Evaluated Option]
* **Positive:** Describe a major advantage, capability, or benefit offered by this option.
* **Negative:** Describe a major disadvantage, trade-off, or limitation of this option.
* **Rejection Reason:** State the decisive technical or business reason why this option was not
  selected.

### Option 3: [Chosen Option Name]
* **Positive:** Describe the primary advantage that makes this option the winning choice.
* **Positive:** Describe secondary architectural or developer experience gains.
* **Negative:** Describe the accepted limitation, risk, or technical debt introduced by choosing
  this option.

### Option X: [Name of Additional Option]
* **Positive:** Describe a major advantage, capability, or benefit offered by this option.
* **Negative:** Describe a major disadvantage, trade-off, or limitation of this option.
* **Rejection Reason:** State the decisive technical or business reason why this option was not
  selected.

---

## 6. Consequences & Operational Impact

### Positive Impacts
* Describe gains, architectural improvements, performance enhancements, or new capabilities unlocked
  by this decision.

### Negative Impacts & Technical Debt
* Describe operational complexities, maintenance overhead, limitations, or technical debt accepted
  as a result of this decision.

### Risk Mitigation
* Describe specific strategies, monitoring metrics, or fallback plans used to manage and minimize
  the risks introduced by this choice.

---

## 7. Follow-up Actions & Artifact Updates

* [ ] **Documentation Updates:** Update system architecture diagrams, API specs, or repository docs
  (`README.md`, `docs/ARCHITECTURE.md`).
* [ ] **Developer & Agent Guidelines:** Update operational instructions, coding standards, or
  constraint rules (`DEVELOPERS.md`, `AGENTS.md`).
* [ ] **Code & Infrastructure Tasks:** Implement necessary code refactoring, database migrations,
  CI/CD pipeline, or infrastructure changes.
* [ ] **Monitoring & Security Adjustments:** Configure new alerts, metrics dashboards, security
  policies, or automated tests required by this decision.
* [ ] **[Task Category]:** Describe any project-specific follow-up task or team alignment
  requirement.
