# IMPLEMENTATION_RULES.md

> Version: 1.0

> Project Codename: CommunicationGym

---

# Purpose

This document defines the implementation standards for CommunicationGym.

Every AI coding assistant and every human engineer must follow these rules.

The goal is consistency.

Implementation should never redefine product decisions.

Those decisions already exist in the documentation.

---

# Source of Truth

The implementation order of authority is:

```text
Product Manifesto

↓

Vision

↓

PRD

↓

Database

↓

AI System

↓

Backend Architecture

↓

Design System

↓

Implementation Rules

↓

Generated Code
```

If generated code conflicts with documentation,

documentation wins.

---

# General Rule

Never invent product behavior.

If behavior is not documented,

stop implementation and request clarification.

Do not guess.

---

# Product Rules

Never:

Invent features.

Invent pages.

Invent workflows.

Invent scoring systems.

Invent AI prompts.

Invent onboarding steps.

Invent navigation.

Everything must originate from repository documentation.

---

# Design Rules

Never invent:

Colors.

Spacing.

Typography.

Shadows.

Components.

Animations.

Use only values defined inside:

DESIGN_TOKENS.md

COMPONENT_LIBRARY.md

MOTION_SYSTEM.md

COPY_GUIDE.md

---

# Component Rules

Always reuse components.

Never duplicate components.

If a new component becomes necessary:

1. Update COMPONENT_LIBRARY.md

2. Obtain approval

3. Build component

Never bypass the design system.

---

# File Structure

Follow feature-first organization.

Example

```text
src/

app/

components/

features/

lib/

hooks/

types/

services/

utils/

styles/
```

Avoid deeply nested folders.

Prefer clarity.

---

# Naming

Variables

camelCase

Functions

camelCase

Components

PascalCase

Database Tables

snake_case

Database Columns

snake_case

Constants

UPPER_SNAKE_CASE

API Routes

kebab-case

Consistency is mandatory.

---

# TypeScript

TypeScript strict mode.

Avoid:

any

Prefer:

Interfaces

Types

Generics

Discriminated unions

Every exported function should have explicit types.

---

# React

Prefer:

Functional components.

Server Components where appropriate.

Client Components only when necessary.

Avoid unnecessary state.

Avoid prop drilling.

Prefer composition.

---

# State Management

Local state

React.

Server state

TanStack Query.

Authentication

Supabase.

Global state only when genuinely required.

Avoid unnecessary complexity.

---

# API Rules

Frontend never communicates directly with AI providers.

Frontend only communicates with backend APIs.

Business logic belongs on the server.

---

# Database Rules

Never write SQL inline inside components.

Database access belongs in dedicated service layers.

Always use migrations.

Never modify production schema manually.

---

# AI Rules

Prompts belong in versioned modules.

Never embed prompts inside React components.

Never duplicate prompts.

Every AI response must be schema validated.

---

# Security Rules

Never expose:

Service Role Keys.

Provider Keys.

Secrets.

Tokens.

Private Storage URLs.

Validate every request.

Trust nothing from the client.

---

# Error Handling

Every asynchronous operation must handle:

Loading.

Success.

Failure.

Retry.

Timeout.

Cancellation where appropriate.

Silent failures are unacceptable.

---

# Accessibility

Every screen must support:

Keyboard navigation.

Visible focus.

Screen readers.

Color contrast.

Reduced motion.

Touch targets ≥48px.

Accessibility is part of implementation,

not polish.

---

# Performance

Lazy-load heavy modules.

Optimize images.

Avoid unnecessary re-renders.

Memoize only when profiling justifies it.

Never optimize prematurely.

Measure first.

---

# Code Quality

Every Pull Request should improve the codebase.

Leave the project cleaner than you found it.

Avoid duplication.

Prefer readability over cleverness.

Comments explain "why,"

not "what."

---

# Testing

Minimum expectations:

Critical business logic.

AI response validation.

Database services.

Authentication.

Progression calculations.

Future additions:

Integration tests.

End-to-end tests.

Performance tests.

Accessibility tests.

---

# Git Workflow

Every feature:

Separate branch.

Small commits.

Clear commit messages.

Example

```text
feat: implement workout evaluation pipeline

fix: prevent duplicate xp awards

refactor: extract coach service

docs: update ai architecture
```

Never commit generated secrets or environment files.

---

# Migrations

Every schema change requires:

Migration file.

Rollback plan.

Documentation update.

Testing in staging.

Schema changes should be deterministic.

---

# Logging

Log:

Errors.

Warnings.

Processing times.

Job execution.

Never log:

Passwords.

Tokens.

Private transcripts.

Audio URLs.

Personally sensitive information.

---

# Monitoring

Track:

API latency.

Queue depth.

Worker failures.

Evaluation success.

Storage usage.

Application crashes.

Observability is mandatory.

---

# Dependencies

Before adding a dependency ask:

Can the platform already do this?

Can we implement it ourselves simply?

Is the dependency actively maintained?

Does it increase bundle size significantly?

Avoid dependency bloat.

---

# Documentation

Whenever implementation changes architecture:

Update documentation first.

Then update code.

Documentation should never lag behind implementation.

---

# AI Coding Rules

AI assistants must:

Read documentation before writing code.

Generate production-ready code.

Avoid placeholder implementations.

Avoid TODO comments unless explicitly requested.

Avoid mock business logic.

Ask questions instead of inventing behavior.

Treat documentation as the specification.

---

# Definition of Done

A feature is complete only when:

Requirements implemented.

Types complete.

Errors handled.

Accessibility verified.

Responsive.

Tests passing.

Documentation updated.

No obvious technical debt introduced.

---

# Non-Negotiable Principles

Never sacrifice correctness for speed.

Never sacrifice maintainability for convenience.

Never sacrifice privacy for features.

Never sacrifice user trust for engagement.

Never sacrifice product consistency for implementation shortcuts.

---

# Engineering Philosophy

The codebase should feel like it was written by one experienced engineer,

not assembled by multiple AI assistants.

Every file should follow the same conventions.

Every component should feel familiar.

Every API should behave predictably.

Consistency compounds.

---

# Final Principle

CommunicationGym is not built by prompts.

It is built by disciplined engineering.

AI assists implementation.

It does not replace architecture, product thinking, or engineering judgment.

Every line of code should move the product one step closer to helping people become confident communicators.
