---
name: local-pr-review
description: "Review pull request diffs or selected code snippets in TypeScript or C# codebases. Use when: reviewing PR changes locally, checking code consistency with repo patterns, detecting code duplication, producing structured PR feedback with verdict."
---

# PR Review Skill

A structured process for reviewing pull request diffs or selected code snippets in a TypeScript or C# codebase. Produces **chat-only feedback** — no file edits.

## Review Workflow

### 1. Gather Context

- If reviewing the full PR, run `git diff main...HEAD --name-only` (or `dev` if the user specifies) to identify changed files, then `git diff main...HEAD` to read the actual diff.
- If reviewing selected code, read the full file and surrounding files for context.
- Identify a reference standard by searching for code with similar functionality (e.g., a related service, class, or module) to use as the baseline for consistency checks.

### 2. Check Consistency with Repo Patterns

Search for and compare against existing code to verify:

- **Class/module structure**: constructors, method signatures, property definitions, interface implementations — match the shape used by similar classes or modules in the codebase.
- **Naming conventions**: follow existing conventions for variables, methods, parameters, and types. Check if similar names/patterns exist elsewhere and use them consistently.
- **Service and API call patterns**: use of existing service wrappers, HTTP client abstractions, request configuration, URL construction, and error handling — match what similar services or repositories already do.
- **Test file structure**: `describe`/`it` blocks (TypeScript/Jest/Mocha) or `[Test]`/`[Fact]` attributes (C#/xUnit/NUnit), mocking/stubbing patterns, test naming conventions, and assertion styles. Compare directly to sibling test files in the same area.
- **Documentation**: XML doc comments (C#) or JSDoc/TSDoc (TypeScript) on public members; README or changelog updates if observable behaviour changes. Compare to existing documentation in the same module or feature area.
- **Imports and dependencies**: prefer existing shared utilities and abstractions over inline logic. Check whether a needed helper already exists before expecting a new one to be introduced.
- **Error handling**: follow the established patterns (exceptions, result/option types, error codes) used by similar classes or modules — do not mix strategies.
- **Logging and output**: use the project's established logging abstraction (e.g., `ILogger` injection in C#, a shared logger utility in TypeScript) — never raw `console.log` or `Console.WriteLine`.

### 3. Detect Code Duplication

This is critical. For every non-trivial block of logic in the PR:

- Search the codebase for similar logic (API calls, data transformations, validation, URL construction).
- If equivalent logic already exists in a utility method, helper, or another module, flag it and suggest reusing the existing code.
- Pay special attention to: URL builders, ID resolvers, permission checks, formatting helpers, common API patterns.

### 4. Check for logical errors and potential bugs

Review the code for common logical errors, edge cases, and potential bugs. Consider whether the code handles error conditions gracefully, whether it correctly implements the intended functionality, and whether there are any scenarios that may not be properly accounted for.

## Output Format

Structure your review response as follows:

### Summary

One-paragraph overview of what the PR does and overall assessment.

### Consistency Issues

Numbered list of places where the code deviates from established repo patterns. For each:

- What the PR does
- What the repo convention is (with file path references to existing examples)
- Suggested alignment

### Duplication Concerns

Numbered list of logic that duplicates existing code. For each:

- The duplicated logic in the PR
- Where the existing equivalent lives (file path + function/method name)
- How to reuse it

### Other Observations

Any additional feedback: edge cases, missing tests, unclear naming, documentation gaps.

### Verdict

A short final assessment: **Looks Good**, **Minor Issues**, or **Needs Changes** — with a brief justification.