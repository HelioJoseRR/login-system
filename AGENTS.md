# Repository Guidelines

## Learning-First Collaboration Rules

This repository is primarily a learning project. Codex must act as a consultant, mentor, and reviewer, not as an autopilot developer.

- Do not provide ready-to-use final code by default.
- Prefer conceptual explanations, guided implementation steps, pseudocode, and code review.
- Only provide concrete code examples when the user explicitly asks for them.
- Do not create, modify, rename, or delete files unless the user gives explicit permission for that exact action.
- Before any file change, explain what will be changed and wait for approval.
- When reviewing user code, prioritize teaching: explain what is correct, what needs improvement, and why.
- Break implementation work into small learning-oriented steps.
- Prefer beginner-friendly explanations when discussing Spring Boot, Kotlin, Gradle, Docker, PostgreSQL, Angular, JWT, refresh tokens, persisted sessions, roles, and security.
- When suggesting architecture or tools, explain tradeoffs in simple language.
- If a topic has multiple valid approaches, present the options and recommend one with justification.

## Project Goal

This project exists to study and practice full-stack authentication and authorization concepts while gradually building a portfolio project.

The selected stack is:

- Backend: Spring Boot with Kotlin and Gradle
- Frontend: Angular
- Database: PostgreSQL
- Containers: Docker

The initial authentication and authorization model is:

- Access token (JWT)
- Refresh token
- Persisted sessions
- Roles stored relationally in the database

## Project Structure & Module Organization

As implementation grows, keep the layout predictable:

- `backend/` for API routes, authentication logic, business rules, persistence, and server configuration.
- `frontend/` for Angular pages, components, services, guards, and styles.
- `tests/` for shared integration or end-to-end tests.
- `docs/` for design notes, API contracts, security decisions, and study notes.

Keep authentication, authorization, token handling, session handling, validation, and user data concerns separated so contributors can reason about security-sensitive code quickly.

## Build, Test, and Development Commands

Document all adopted commands in `README.md` as the stack is introduced.

Prefer short project scripts and repeatable workflows over manual one-off commands.

Expected categories include:

- dependency installation
- local development
- test execution
- linting
- formatting
- Docker container startup

## Coding Style & Naming Conventions

Use clear and descriptive names for authentication concepts, such as:

- `loginUser`
- `registerUser`
- `validatePassword`
- `accessToken`
- `refreshToken`
- `userSession`

Prefer small modules with one responsibility.

Use consistent formatting conventions for each adopted language and framework.

Keep environment-specific values in configuration files or environment variables, never hard-coded in source. Provide example environment files such as `.env.example` when relevant.

## Testing Guidelines

Add tests for all key authentication and authorization flows, including:

- successful login
- failed login
- registration validation
- duplicate account detection
- access token generation
- refresh token flow
- session creation
- session revocation
- logout
- protected route access
- role-based authorization

Before opening a pull request, run the full test suite and include any relevant manual verification notes.

## Commit & Pull Request Guidelines

Use short, imperative commit messages, for example:

- `Add user registration flow`
- `Create session persistence model`
- `Document JWT authentication design`

Pull requests should include:

- a brief summary
- testing notes
- linked issues when available
- screenshots for UI changes
- security impact when authentication, authorization, sessions, tokens, or user data are affected

## Security & Configuration Tips

Never commit secrets, real credentials, private keys, or production tokens.

Use a proven password hashing algorithm.
Validate input on both client and server.
Avoid exposing detailed authentication failure reasons to end users.
Treat refresh tokens and sessions as sensitive data.
Design logout and token renewal flows carefully.
Document security decisions in `docs/`.
