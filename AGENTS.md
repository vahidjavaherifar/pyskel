# AGENTS.md — AI Agent Guidance & Execution Rules

This document defines mandatory operational constraints, architectural baselines, environment
workflows, and execution protocols for AI coding assistants and automated agents operating on this
repository.

> **Crucial Rule:** Always read this document along with [DEVELOPERS.md](./DEVELOPERS.md) prior to
proposing, generating, or modifying code within this codebase.

---

## 1. Context & Scope Allocation

* **Target Purpose:** Core application domain, execution runtime, and modular codebase boundaries.
* **No Speculative Assumptions:** If an implementation detail, configuration key, or architectural
  decision is ambiguous, ask for explicit clarification or consult [DEVELOPERS.md](./DEVELOPERS.md)
  and [docs/ARCHITECTURE.md](./docs/ARCHITECTURE.md). Do not invent unverified patterns or assume
  implicit logic.

---

## 2. Core Execution Constraints

AI agents must strictly adhere to the following hard constraints:

1. **Non-Destructive Editing:**
   - Do NOT delete, refactor, or rewrite working existing code unless explicitly requested.
   - Do NOT introduce unused functions, speculative abstractions, or placeholder `TODO`
     implementations.
2. **Deterministic & Concise Code:**
   - Write clean, self-contained, and readable code without fluff.
   - Prefer explicit error handling over unhandled panics or silent failures.
3. **Dependency Discipline:**
   - Do NOT add new third-party packages, external libraries, or crates without explicit
     confirmation.
   - Rely strictly on established dependencies defined in standard workspace configuration files.
4. **File System Boundaries:**
   - Never generate temporary output files, build artifacts, or local configuration files inside the
     source tree unless mandated by the build pipeline.

---

## 3. Project Context & Documentation Map

Before modifying files, locate contextual rules and domain specifications in the following standard
documentation:

* **Engineering Rules & Workflows:** Refer to [DEVELOPERS.md](./DEVELOPERS.md).
* **System Architecture & Boundaries:** Refer to [docs/ARCHITECTURE.md](./docs/ARCHITECTURE.md).
* **Architectural Decision Logs:** Refer to [docs/ADR.md](./docs/ADR.md).
* **Release & Versioning Tracking:** Refer to [CHANGELOG.md](./CHANGELOG.md).

---

## 4. Operational Commands & Environment Workflows

Agents executing terminal, build, or test tasks must strictly adhere to the following execution
patterns:

### Dev Environment Navigation & Scaffolding

* **Targeted Operations:** Avoid scanning the directory tree with raw `ls` or recursive searches.
  Use workspace tooling and package runners to jump directly to specific workspace components.
* **Dependency Isolation:** Ensure new modules or sub-packages are explicitly linked to the
  workspace root so language servers, linters, and type-checkers acknowledge them immediately.
* **Package Identifiers:** Always verify the internal module package configuration
  (e.g., `package.json`, `Cargo.toml`, or `pyproject.toml`) for exact project names rather than
  relying on folder paths.

### Testing & Verification Protocols

* **CI Pipeline Alignment:** Always inspect pipeline definitions under `.github/workflows/` to
  understand the exact verification gates enforced during integration.
* **Scoped Test Execution:** Run scoped test suites for modified packages/modules before executing
  full repository checks.
* **Targeted Test Execution:** When focusing on a specific failing test, pass direct name or pattern
  matching flags to the underlying test runner
  (e.g., `pnpm vitest run -t "<test_name>"`, `cargo test <test_name>`, or `pytest -k <test_name>`).
* **Post-Refactor Validation:** After moving files or altering imports, execute static analysis and
  linter tooling to ensure no hidden type or lint regressions exist.
* **Test Coverage Mandatory Rule:** Always create or update unit/integration tests for any
  introduced code changes, regardless of whether it was explicitly requested.

---

## 5. Contribution & Communication Standards

### Pull Request & Commit Rules

* **PR Title Format:** Maintain strict scope prefixing: `[<project_name_or_scope>] <Title>`
* **Pre-commit Gate:** Never generate or submit a commit or Pull Request until all local lint,
  type-check, and test commands pass cleanly with zero errors.

### Output Formatting

* **Minimal Conversational Overhead:** Do not generate long preambles, marketing fluff, or generic
  tutorials. Provide direct solutions immediately.
* **Surgical Diff / Edits:** Focus strictly on modified code segments unless a complete file rewrite
  is explicitly requested.
* **Explicit Change Reason:** Provide a 1-2 sentence concise explanation highlighting *why* a
  specific code decision was made.
