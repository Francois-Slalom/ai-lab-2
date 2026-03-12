# Functional Requirements

## Purpose

This document defines the core functional requirements for the TODO application. The intent is to make the expected user-facing behavior explicit so the frontend, backend, and tests can be built against the same scope.

## Core Requirements

1. The application must allow a user to create a new task by entering a title.
2. The application must prevent a task from being created if the title is empty.
3. The application must display a list of all saved tasks.
4. The application must allow a user to mark a task as completed.
5. The application must allow a user to mark a completed task as not completed.
6. The application must allow a user to edit an existing task, including its title, description, and due date.
7. The application must allow a user to delete a task.
8. The application must allow a user to assign an optional due date to a task.
9. The application must visually distinguish completed tasks from active tasks.
10. The application must sort tasks so that active tasks appear before completed tasks.
11. Within each status group, the application must sort tasks by due date, with the earliest due date shown first.
12. Tasks without a due date must appear after tasks that do have a due date within the same status group.
13. The application must preserve tasks between sessions so that reloading the app does not remove existing tasks.
14. The application must show enough task information in the list view for a user to understand the title, completion status, and due date of each task.
15. The application must provide clear feedback when a task is added, updated, or deleted.

## Scope Notes

- A due date is optional, not required.
- A task title is required.
- Sorting behavior is intentional and should be consistent across the application.
- The initial scope assumes a single user managing their own task list.
