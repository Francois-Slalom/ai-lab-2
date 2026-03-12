# Testing Guidelines

## Purpose

This document defines the testing principles and standards for the TODO application. The goal is to keep the test suite reliable, maintainable, and aligned with the project structure so new features can be implemented with clear quality expectations.

## Core Principles

1. All new features and bug fixes must include appropriate automated tests.
2. Tests must be maintainable, readable, and focused on behavior rather than implementation details.
3. Tests must be isolated and independent so they can run in any order.
4. Test suites must support repeated execution without relying on leftover state from previous runs.
5. Setup and teardown hooks must be used where needed so tests remain deterministic across multiple runs.

## Unit Tests

1. Use Jest to test individual functions and React components in isolation.
2. Unit test files must use the naming convention `*.test.js` or `*.test.ts`.
3. Backend unit tests must be placed in `packages/backend/__tests__/`.
4. Frontend unit tests must be placed in `packages/frontend/src/__tests__/`.
5. Unit test files should be named to match what they are testing, for example `app.test.js` for `app.js`.
6. Unit tests should focus on small, well-defined behaviors and edge cases.

## Integration Tests

1. Use Jest and Supertest to test backend API endpoints with real HTTP requests.
2. Integration test files must use the naming convention `*.test.js` or `*.test.ts`.
3. Integration tests must be placed in `packages/backend/__tests__/integration/`.
4. Integration test files should be named based on the behavior or endpoint they cover, for example `todos-api.test.js`.
5. Integration tests should verify request handling, response status codes, response payloads, and error behavior.

## End-to-End Tests

1. Use Playwright for end-to-end testing of complete UI workflows.
2. E2E test files must use the naming convention `*.spec.js` or `*.spec.ts`.
3. E2E tests must be placed in `tests/e2e/`.
4. E2E test files should be named after the user journey they cover, for example `todo-workflow.spec.js`.
5. Playwright tests must use one browser only.
6. Playwright tests must use the Page Object Model (POM) pattern for maintainability.
7. E2E coverage must be limited to 5-8 critical user journeys, focused on happy paths and important edge cases rather than exhaustive permutations.
8. E2E tests should verify the behaviors that matter most to users, including task creation, editing, completion, deletion, persistence, and sorting when implemented.

## Environment And Port Configuration

1. Applications must use environment variables with sensible defaults for port configuration.
2. The backend should use `const PORT = process.env.PORT || 3030;`.
3. The frontend should default to port 3000 and allow override through the `PORT` environment variable.
4. Port configuration must support CI and automated test environments where ports may be assigned dynamically.

## Reliability Requirements

1. Every test must create or arrange its own required data and must not depend on another test having run first.
2. Shared setup utilities are allowed only when they improve clarity and do not hide important test behavior.
3. Cleanup must be explicit when a test creates temporary files, mock servers, persisted data, or browser state.
4. Flaky tests are not acceptable and must be fixed before new work depends on them.

## Maintainability Standards

1. Tests should use descriptive names that explain the behavior under test.
2. Test code should avoid unnecessary duplication while still remaining easy to read.
3. Assertions should be specific enough to catch regressions without being brittle.
4. When a feature changes, the related tests must be updated as part of the same work.
5. Prefer a smaller number of high-value tests over a large number of shallow or redundant tests.
