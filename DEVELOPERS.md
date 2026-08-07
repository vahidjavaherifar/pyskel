# Developer Guide

This document defines the architectural patterns, development environment instructions, quality
standards, security baselines, and operational workflows for contributors and maintainers of this
repository.

> **Note:** For immediate task tracking, refer to [TODO.md](./TODO.md). For long-term project
  planning, refer to [MILESTONES.md](./MILESTONES.md).

---

## 1. Project Architecture & Layout

Document the repository's structural boundaries, core layers, and directory hierarchy below:

```text
.
├── docs/      # Technical specifications, ADRs, and diagrams (optional)
├── src/       # Core source code and business domain logic (e.g., src/, app/, pkg/)
├── tests/     # Automated test suites and mocks (or inline alongside source modules)
└── README.md  # Project overview and entry point documentation
```

### Architectural Principles

* **Separation of Concerns:** Keep core domain logic decoupled from external interfaces and
  infrastructure.
* **Single Responsibility:** Design modules and packages around single, clearly defined
  capabilities.
* **Minimal Coupling:** Prefer explicit dependency passing over hidden global states.
* **Architecture Decision Records (ADRs):** Document all major architectural decisions and
  trade-offs under target documentation paths (e.g., `docs/adr/`).

---

## 2. Development Environment

### System Prerequisites

List all required runtimes, compilers, system packages, and external services:

* **Core Runtime / Compiler:** Language toolchain and version specification.
* **Package / Build Manager:** Dependency management and build automation tools.
* **Version Control System:** Source control client and authentication configuration.
* **Infrastructure Dependencies:** External databases, key-value stores, or runtime services.

### Environment Setup

1. **Obtain Source Code:**
   Retrieve the codebase using your version control tool.
2. **Configure Local Environment:**
   Copy configuration templates (e.g., `.env.example`) to local configuration files and set target
   variables.
3. **Install Dependencies:**
   Execute standard dependency resolution and toolchain installation commands.
4. **Initialize Local Services:**
   Start any required background services or local container instances.

---

## 3. Standard Operational Commands

Document the primary execution commands used during the local development lifecycle:

| Workflow | Operation | Description |
| :--- | :--- | :--- |
| **Setup** | Dependency Setup | Installs local tools, compilers, and library dependencies. |
| **Execution** | Run Application | Launches the application or service in local development mode. |
| **Formatting** | Code Format | Automatically formats source code to match project style rules. |
| **Linting** | Static Analysis | Runs static analyzers and checks for potential bugs or code smells. |
| **Testing** | Execute Tests | Runs unit, integration, and regression test suites. |
| **Benchmarking** | Performance Test | Measures performance-critical paths and hotspots. |
| **Build** | Compilation / Packaging | Compiles source assets or builds distribution binaries/packages. |
| **Cleanup** | Clean Artifacts | Removes build caches, temporary assets, and execution logs. |

---

## 4. Engineering & Code Standards

### Design & Clean Code Rules

* **Code Clarity:** Write self-documenting code. Use comments to explain *why* a decision was made,
  not *what* the code does.
* **Function Granularity:** Keep functions small, focused, and predictable.
* **Dead & Commented Code:** Remove dead code, unused abstractions, and commented-out blocks before
  submitting code.

### Error Handling & Reliability

* **Explicit Errors:** Handle edge cases explicitly. Avoid unhandled crashes or unrecoverable states
  in production environments.
* **Context Preservation:** Provide informative context when handling or re-throwing errors.

### Performance Guidelines

* **Allocation Efficiency:** Minimize unnecessary object or memory allocations in hot code paths.
* **Data-Driven Optimization:** Measure and benchmark before attempting optimizations; avoid
  premature tuning.
* **Critical Path Benchmarking:** Maintain performance benchmarks for resource-intensive or
  latency-sensitive modules.

---

## 5. Security & Confidentiality

* **Input Validation:** Validate and sanitize all external inputs. Never trust client-supplied data
  without verification.
* **Parameterized Queries:** Always use parameterized or prepared statements for storage and
  database operations.
* **Secret Isolation:** Store secrets, API keys, and credentials strictly outside the codebase; rely
  on environment injection.
* **Least Privilege:** Enforce minimal permission boundaries across services, storage layers, and
  system processes.
* **Confidentiality:** Ensure credentials, authorization tokens, and PII are redacted from log
  outputs.

---

## 6. Dependency Management

* **Stability Preference:** Favor stable, well-maintained libraries over experimental dependencies.
* **Dependency Minimization:** Keep dependency counts low and minimize transitive dependencies.
* **Lifecycle Maintenance:** Regularly purge unused packages and keep active dependency versions up
  to date.

---

## 7. Quality Assurance & Documentation

### Testing Spectrum

Every implementation or bug fix must be validated through appropriate testing layers:

* **Unit Tests:** Verify individual functions, modules, and isolated domain logic.
* **Integration Tests:** Validate interactions between internal components, databases, or network
  protocols.
* **Regression Tests:** Include test cases verifying that fixed bugs cannot reoccur.

### Documentation Triggers

Update relevant documentation whenever:

- Public APIs or interface models are modified.
- High-level architecture or data flow changes.
- Environment variables, configuration schema, or build processes update.

---

## 8. Continuous Integration (CI)

Every Pull / Merge Request submitted to the repository must automatically trigger CI automation jobs
verifying:

* **Automated Code Formatting:** Ensures all source files adhere strictly to style guidelines.
* **Linting & Code Style:** Enforces static style rules and syntax invariants.
* **Static Analysis:** Scans for potential memory leaks, type errors, or security vulnerabilities.
* **Unit Test Suite Execution:** Verifies isolated business logic components.
* **Integration Test Suite Execution:** Validates cross-module interactions and system boundaries.

---

## 9. Repository Standards & Code Review

### Repository Hygiene

* **Atomic Commits:** Structure commits around logical, self-contained, and atomic changes.
* **Generated Artifacts:** Do not commit compiled binaries, generated assets, or build artifacts
  unless explicitly mandated.

### Code Review Guidelines

Maintainers and reviewers must evaluate code against the following baseline:

* **Correctness:** Does the implementation meet functional specifications without regressions?
* **Readability:** Is the structure clear, logical, and maintainable for other engineers?
* **Performance:** Does it avoid runtime bottlenecks and unnecessary resource consumption?
* **Security:** Are input boundaries, storage queries, and credential handling secure?
* **Test Coverage:** Are unit, integration, or regression tests included and passing?
* **Documentation:** Are public APIs, inline comments, and specifications updated?

---

## 10. Contribution & Branching Workflow

### Branch Strategy

Maintain a clean and traceable version history using structured long-lived branches and work branch
prefixes:

* **Long-Lived Branches:**
  - `main` : Production-ready code.
  - `dev`  : Active integration branch for ongoing development.

* **Work Branches:**
  - `feat/description`     : New capabilities or functional additions.
  - `fix/description`      : Bug fixes and immediate patches.
  - `refactor/description` : Internal code restructuring without behavioral changes.
  - `perf/description`     : Performance optimization changes.
  - `test/description`     : Adding or updating tests.
  - `docs/description`     : Technical documentation updates or additions.
  - `ci/description`       : CI/CD configuration and pipeline updates.
  - `chore/description`    : Maintenance, tooling updates, or configuration polish.

### Commit Standards

Write clear and structured commit messages following a consistent baseline:

`<type>(<scope>): <short summary>`

[optional detailed context on why the change was made]

[optional issue reference or tracking metadata]

### Pull / Merge Request Checklist

Before merging changes into protected branches:

1. All automated CI pipelines pass cleanly (Formatting, Linting, Analysis, Tests).
2. Code is up to date with the target base branch.
3. Documentation and inline specifications are updated.
4. Changes have been reviewed and approved by at least one maintainer.

---

## 11. Release & Versioning

Follow standard Semantic Versioning (`MAJOR.MINOR.PATCH`) principles for release management:

1. **Pre-release Check:** Confirm all verification checks pass on candidate branches.
2. **Changelog Maintenance:** Document structural changes, additions, and deprecations in
   `CHANGELOG.md`.
3. **Version Bump:** Update the application version indicator in project configuration files.
4. **Release Tagging:** Create a version-tagged snapshot in version control to track the release.

---

## 12. Associated Documentation & References

- [ADR.md](./docs/ADR.md) — Log of Architectural Decision Records documenting critical design
  choices and trade-offs.
- [AGENTS.md](./AGENTS.md) — Operational instructions, code generation rules, and scope boundaries
  for AI coding agents.
- [ARCHITECTURE.md](./docs/ARCHITECTURE.md) — High-level system design, module interactions, and
  boundary isolation specs.
- [CHANGELOG.md](./CHANGELOG.md) — Chronological history of release versions, breaking changes, and
  updates.
- [CODE_OF_CONDUCT.md](./docs/CODE_OF_CONDUCT.md) — Ethical standards, community interaction
  guidelines, and enforcement rules.
- [CODEOWNERS](.github/CODEOWNERS) — File-level ownership mappings and automatic review allocation
  rules.
- [CONTRIBUTING.md](./CONTRIBUTING.md) — Guidelines for submitting patches, code review
  requirements, and PR workflows.
- [DEVELOPERS.md](./DEVELOPERS.md) — Comprehensive developer entry point, engineering baselines, and
  execution protocols.
- [FAQ.md](./docs/FAQ.md) — Frequently asked questions regarding development setup, execution, and
  troubleshooting.
- [GOVERNANCE.md](./docs/GOVERNANCE.md) — Decision-making framework, role responsibilities, and
  maintainer authority limits.
- [LICENSE](./LICENSE) — Legal framework, usage rights, and software distribution terms.
- [MILESTONES.md](./MILESTONES.md) — Strategic roadmap, version targets, and long-term project
  objectives.
- [README.md](./README.md) — High-level orientation, core features, and project initialization.
- [SECURITY.md](./SECURITY.md) — Vulnerability disclosure policy, security standards, and reporting
  protocols.
- [TODO.md](./TODO.md) — Active short-term task queue, technical debt tracking, and immediate
  metrics.
