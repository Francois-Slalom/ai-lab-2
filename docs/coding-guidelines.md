# Coding Guidelines

## Purpose

This document summarizes the coding style and quality principles for the TODO application. The intent is to keep the frontend, backend, and tests consistent, readable, and easy to maintain as the project evolves.

## General Style

Code should favor clarity over cleverness. A reader should be able to understand the purpose of a module, function, or component quickly without having to reverse-engineer compact or overly abstract code.

Formatting should stay consistent throughout the repository. Use standard JavaScript conventions, keep indentation and spacing uniform, and avoid mixing multiple styles in the same file. Long expressions should be wrapped in a way that keeps the structure readable rather than minimizing line count.

Naming should be explicit. Variables, functions, and components should use names that describe their role in the domain. Avoid vague names such as `data`, `value`, or `item` when a more specific name would make the code easier to follow.

## File And Module Organization

Each file should have a clear responsibility. If a file starts handling unrelated concerns, split it into smaller modules. Frontend components should focus on UI behavior and presentation, while backend modules should keep request handling, validation, and data access separated where practical.

Imports should be organized consistently. Group external dependencies first, then internal modules, then styles when applicable. Avoid unused imports, and remove dead code promptly.

Exports should remain simple and predictable. Prefer one primary responsibility per module, and avoid files that expose unrelated helpers without a clear reason.

## React And Frontend Practices

React components should be small enough to read in one pass. If a component grows to include too much state management, data fetching, rendering logic, and event handling, extract the relevant pieces into smaller components or helper functions.

Component logic should focus on user behavior, not implementation tricks. State should be kept as local and as simple as possible. Derived values should be computed clearly instead of duplicated across the component.

UI code should avoid unnecessary duplication. Repeated markup, styling patterns, or behavior should be extracted into reusable components or helpers when that reduces maintenance cost.

## Backend Practices

Backend code should validate inputs explicitly and fail safely. Request handlers should return clear status codes and structured responses. Error handling should be deliberate rather than left to implicit runtime failures.

Server-side modules should separate application setup from business behavior where it improves testability. Reusable logic should be extracted from route handlers when the same behavior is used in more than one place.

Configuration should come from environment variables with sensible defaults. Hard-coded environment-specific values should be avoided unless there is a strong reason.

## DRY And Reuse

The DRY principle applies to behavior, not just copied lines. If the same logic appears in multiple places, it should usually be extracted into a shared function, utility, or component. At the same time, avoid premature abstraction. Two small duplicated snippets are often better than a complicated abstraction that hides intent.

Shared utilities should exist because they simplify the codebase, not because every repeated line must be generalized immediately.

## Comments And Documentation

Code should be self-explanatory whenever possible. Comments should be used sparingly and only when they add context that the code itself cannot express clearly, such as intent, constraints, or non-obvious decisions.

Public behaviors, conventions, and cross-cutting decisions should be captured in project documentation rather than repeated as long inline comments.

## Linting And Quality Checks

The project should use linting to enforce consistent style and catch common mistakes early. ESLint is the expected linting tool for JavaScript and React code in this repository.

Lint rules should support readability and correctness, including detection of unused variables, unreachable code, inconsistent imports, and risky patterns. Code should pass linting before it is considered complete.

Automated checks should complement human review. Linting, tests, and any future formatting tools should help maintain consistency, but they do not replace good engineering judgment.

## Maintainability Principles

Changes should be minimal, focused, and related to the task being solved. Avoid refactoring unrelated areas while implementing a feature unless the existing code directly blocks the work.

Functions should do one coherent thing. When a function starts mixing validation, transformation, side effects, and presentation concerns, it should be simplified or broken apart.

Error messages should be specific enough to support debugging and user feedback. Silent failures and ambiguous fallback behavior should be avoided.

When adding a feature, update the related tests and documentation as part of the same change. Code quality includes keeping the surrounding system accurate, not just making the new code work.
