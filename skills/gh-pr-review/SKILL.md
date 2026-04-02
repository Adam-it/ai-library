---
name: gh-pr-review
description: "Review pull request for a given PR from GitHub in TypeScript or C# codebases. Use when: reviewing PR changes locally, checking code consistency with repo patterns, detecting code duplication, producing structured PR feedback with verdict."
---

# PR Review Skill

A structured process for reviewing pull request based on a given PR from GitHub. Before you may proceed clarify if the user provided the repo name and the PR title or number which you need in order to retrieve the PR. Ask for this information if needed. Produces **chat-only feedback** — no file edits. You may add comments to the PR using `github/add_comment_to_pending_review`, `github/add_issue_comment`, or `github/add_reply_to_pull_request_comment` tools, but you should only do so if explicitly instructed by the user. Otherwise, provide all feedback in your chat response. When performing PR review consider every comments in the PR, PR description and related issue description.

## Review Workflow

### 1. Identify the PR

Using GitHub MCP tools, identify the PR to review based on the information provided by the user (repo name + PR title or number). Retrieve the PR diff and all related comments, PR description and related issue description to gather the full context for your review.

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