# BACKEND_ARCHITECTURE.md

> Version: 0.1
>
> Project Codename: CommunicationGym

---

# Purpose

The backend powers the CommunicationGym platform.

It is responsible for authentication, workout management, recording ingestion, AI orchestration, progress tracking, notifications and platform integrity.

The backend should remain modular, observable and scalable.

Business logic belongs in backend services.

The frontend should remain lightweight.

---

# Engineering Philosophy

The backend should be:

Simple.

Reliable.

Observable.

Scalable.

Replaceable.

No single service should become a bottleneck.

Every service should have one clearly defined responsibility.

---

# High-Level Architecture

```text
                Frontend (Next.js)

                      │

          Authentication (Supabase)

                      │

        Backend API (Next.js Route Handlers)

                      │

      ┌───────────────┼────────────────┐

      │               │                │

 Workout Service   Coach Service   Progress Service

      │               │                │

      └───────────────┼────────────────┘

                      │

             Background Job Queue

                      │

        ┌─────────────┼──────────────┐

        │             │              │

 Speech Engine   AI Evaluation   Notification Worker

                      │

                PostgreSQL

                      │

             Supabase Storage
```

---

# Recommended Tech Stack

Frontend

Next.js

TypeScript

Tailwind CSS

shadcn/ui

Framer Motion

---

Authentication

Supabase Auth

Google OAuth

Future

Apple

Microsoft

GitHub

---

Database

Supabase PostgreSQL

---

Object Storage

Supabase Storage

---

Background Jobs

Trigger.dev (Recommended)

Future alternative

Inngest

Temporal

BullMQ (Self-hosted)

---

AI Providers

Speech Recognition

Deepgram / Whisper

Reasoning

OpenAI

Anthropic

Future Local Models

---

Deployment

Vercel

Background Worker

Railway / Fly.io / Render

---

Monitoring

Sentry

PostHog

OpenTelemetry (Future)

---

# Backend Services

The backend is divided into independent services.

---

## Authentication Service

Responsibilities

Login

Logout

Session validation

JWT verification

Profile creation

---

## Workout Service

Responsibilities

Assign daily workout

Reroll logic

Workout history

Workout completion

Workout scheduling

---

## Recording Service

Responsibilities

Upload audio

Validate file

Store metadata

Queue processing

Storage cleanup

---

## Coach Service

Responsibilities

Create evaluation jobs

Build prompt context

Execute Coach Engine

Validate responses

Store evaluation reports

---

## Progress Service

Responsibilities

XP

Levels

Ranks

Achievements

Streaks

Leaderboard updates

---

## Recommendation Service

Responsibilities

Select tomorrow's workout

Read Communication DNA

Balance difficulty

Prevent repetition

Future curriculum engine

---

## Notification Service

Responsibilities

In-app notifications

Email notifications

Push notifications (Future)

Reminder scheduling

---

# API Philosophy

The frontend never talks directly to AI providers.

The frontend communicates only with backend APIs.

The backend owns:

Business logic

Validation

Authorization

AI orchestration

Progression

---

# API Design Rules

REST-first.

Predictable.

Versioned.

Resource oriented.

---

Example

```text
/api/v1/
```

Never expose internal implementation details.

---

# Suggested API Structure

```text
/api/v1

/auth

/profile

/workouts

/recordings

/evaluations

/history

/progress

/leaderboard

/settings

/notifications

/admin
```

Future APIs should follow the same convention.

---

# Example Endpoints

Authentication

```text
POST /auth/login

POST /auth/logout

GET /auth/session
```

---

Profile

```text
GET /profile

PATCH /profile
```

---

Workout

```text
GET /workouts/today

POST /workouts/reroll

POST /workouts/start

POST /workouts/complete
```

---

Recording

```text
POST /recordings/upload

GET /recordings/{id}
```

---

Evaluation

```text
GET /evaluations/{sessionId}
```

---

History

```text
GET /history

GET /history/{id}
```

---

Progress

```text
GET /progress
```

---

Leaderboard

```text
GET /leaderboard
```

---

Settings

```text
GET /settings

PATCH /settings
```

---

# Authentication Flow

```text
User

↓

Google Login

↓

Supabase Auth

↓

JWT

↓

Backend Validation

↓

Profile Lookup

↓

Authorized Request
```

The frontend never stores sensitive credentials.

Supabase manages authentication.

---

# Authorization

Every API request must verify:

Authentication

Authorization

Ownership

Permissions

Validation

Business Rules

Never trust frontend input.

---

# Validation

Every endpoint validates:

Authentication

Request schema

Business rules

Ownership

Rate limits

File size

Content type

Invalid requests return structured error responses.

---

# Error Format

Every API should return consistent JSON.

Example

```json
{
  "success": false,
  "error": {
    "code": "WORKOUT_NOT_FOUND",
    "message": "Today's workout could not be found."
  }
}
```

Never expose stack traces.

Never expose provider errors.

---

# Idempotency

Critical operations should be idempotent.

Examples

Workout completion

Recording upload

XP awards

Achievement unlocks

Retrying a request should never duplicate progress.

---

# API Versioning

Always version public APIs.

Example

```text
/api/v1/
```

Breaking changes require:

New version

Migration plan

Documentation update

---

# Engineering Principles

Backend services should be:

Stateless where possible.

Horizontally scalable.

Observable.

Loosely coupled.

Event driven.

Easy to replace.

---

# Steve Jobs Test

If a new engineer joins tomorrow,

they should understand the backend architecture within one hour.

If not,

the architecture is too complicated.

Simplicity scales better than cleverness.

---

# Final Principle

The backend should quietly handle complexity so the user experiences simplicity.

A user should never think about authentication, queues, AI providers or storage.

They should simply open CommunicationGym,

complete today's workout,

and become a better communicator.


# BACKEND_ARCHITECTURE.md

## Phase 2 — Processing Pipeline, Infrastructure & Reliability

---

# Processing Model

Every expensive operation executes asynchronously.

API requests should remain fast.

Target response time:

< 500 ms

Heavy workloads are delegated to background workers.

---

# Request Lifecycle

```text
Client

↓

API Validation

↓

Database Write

↓

Background Job Created

↓

Immediate Response

↓

Worker Processes Job

↓

Database Updated

↓

Client Receives Status
```

Users should never wait for AI evaluation during the upload request.

---

# Background Job Pipeline

The platform uses a queue-based processing model.

```text
Recording Uploaded

↓

Create Evaluation Job

↓

Transcription Worker

↓

Speech Metrics Worker

↓

Evaluation Worker

↓

Profile Update Worker

↓

Progress Worker

↓

Notification Worker
```

Each worker performs exactly one task.

Workers communicate through the database and job queue.

---

# Worker Responsibilities

## Transcription Worker

Input

Recording

Output

Transcript

Failure Retry

Yes

Maximum Retries

3

---

## Speech Metrics Worker

Input

Transcript + Audio

Output

Speech Metrics

Examples

* Speaking Duration
* Speaking Pace
* Pause Count
* Filler Words

Maximum Retries

2

---

## Evaluation Worker

Input

Transcript

Speech Metrics

Workout Context

Communication Profile

Output

Evaluation Report

Retries

2

---

## Profile Update Worker

Updates:

Communication DNA

Skill Progress

Long-term Statistics

Recommendation Signals

Retries

1

---

## Progress Worker

Responsible for:

XP

Levels

Ranks

Achievements

Leaderboard

Daily Streak

This worker is idempotent.

---

## Notification Worker

Responsible for:

In-app Notifications

Emails

Future Push Notifications

Never blocks the main application.

---

# Queue Design

Every job contains:

```text
Job ID

Job Type

User ID

Reference ID

Status

Retry Count

Created At

Started At

Completed At

Failure Reason
```

Supported States

Queued

Running

Completed

Failed

Retrying

Cancelled

Dead Letter

---

# Dead Letter Queue

Jobs that permanently fail move into a Dead Letter Queue.

Operations can inspect and replay them.

Dead Letter jobs should never be silently discarded.

---

# Idempotency

Workers must be safe to execute multiple times.

Example

Workout Completed

↓

Worker crashes

↓

Worker retries

↓

XP should still be awarded once.

Never rely on the frontend to prevent duplicates.

---

# Transaction Boundaries

Critical operations execute inside database transactions.

Examples

Workout Completion

XP Award

Achievement Unlock

Leaderboard Update

If one step fails,

the transaction rolls back.

---

# Storage Lifecycle

Recording Upload

↓

Virus Validation (Future)

↓

Store in Private Bucket

↓

Metadata Saved

↓

Processing Begins

↓

Evaluation Completed

↓

Recording Available

↓

User Deletes Recording (Optional)

↓

Retention Policy Applied

Storage should always be independent from AI processing.

---

# Rate Limiting

Protect all public endpoints.

Suggested Defaults

Authentication

10 requests / minute

Workout APIs

30 requests / minute

Recording Upload

10 uploads / hour

Evaluation Status

60 requests / minute

Admin APIs

Strict allow-list

Rate limits should be configurable.

---

# File Validation

Accept:

audio/webm

audio/mp4

audio/mpeg

audio/wav

Reject:

Executable files

Unknown MIME types

Oversized uploads

Corrupted recordings

Maximum upload size should be configurable.

---

# Security

Every request passes through:

Authentication

↓

Authorization

↓

Schema Validation

↓

Business Validation

↓

Rate Limiting

↓

Logging

↓

Execution

Never trust client input.

---

# Secrets Management

Never expose:

API Keys

Database Credentials

Service Role Keys

Provider Secrets

Secrets are loaded from environment variables only.

Never commit secrets to Git.

---

# Error Handling

Return consistent responses.

Example

```json
{
  "success": false,
  "error": {
    "code": "EVALUATION_PENDING",
    "message": "Your workout is still being processed."
  }
}
```

Do not expose provider-specific errors to clients.

---

# Retry Strategy

Transient Failures

Retry Automatically

Permanent Failures

Move to Dead Letter Queue

Provider Outage

Pause affected jobs

Resume automatically after recovery

---

# Event Bus

Major system events should be published.

Examples

```text
USER_CREATED

WORKOUT_ASSIGNED

WORKOUT_STARTED

WORKOUT_COMPLETED

RECORDING_UPLOADED

TRANSCRIPT_READY

METRICS_READY

EVALUATION_COMPLETED

PROFILE_UPDATED

LEVEL_UP

ACHIEVEMENT_UNLOCKED

NOTIFICATION_SENT
```

Future services subscribe to events rather than directly calling one another.

---

# Logging

Every service should produce structured logs.

Include:

Timestamp

Request ID

User ID (when available)

Service Name

Duration

Status

Error Code

Sensitive information must never be logged.

---

# Health Checks

Every service exposes a health endpoint.

Minimum Checks

Database

Storage

Queue

AI Provider

Background Worker

Used by deployment platforms for monitoring.

---

# Observability

Track:

API latency

Queue depth

Job duration

Worker failures

Retry count

Evaluation success rate

Storage usage

These metrics are operational and separate from product analytics.

---

# Engineering Rules

Every new service must answer:

* Does it have a single responsibility?
* Can it scale independently?
* Can it fail without crashing the platform?
* Is it observable?
* Is it testable?
* Is it idempotent?

If the answer to any question is "No",

redesign before implementation.

---

# Production Readiness Checklist

Before release verify:

✓ Database migrations applied

✓ RLS policies enabled

✓ Storage policies validated

✓ Environment variables configured

✓ Queue processing healthy

✓ Health endpoints responding

✓ Logging enabled

✓ Monitoring active

✓ Rate limiting configured

✓ Backup completed

---

# Final Principle

The backend should optimize for reliability over cleverness.

A user should never lose progress because an AI provider is slow, a worker crashes, or a queue is temporarily unavailable.

Every subsystem should fail gracefully while preserving the user's work.
# BACKEND_ARCHITECTURE.md

## Phase 3 — Deployment, Operations & Production Readiness

---

# Deployment Philosophy

CommunicationGym should be deployable by a single engineer.

Infrastructure should remain simple until product-market fit.

Avoid complexity that does not improve reliability or user experience.

---

# Production Architecture

```text
                    Users

                      │

               Cloudflare CDN

                      │

                Vercel (Frontend)

                      │

             Next.js Route Handlers

                      │

        ┌─────────────┴─────────────┐

        │                           │

   Supabase                     Trigger.dev
(Database/Auth/Storage)      (Background Jobs)

        │                           │

        └─────────────┬─────────────┘

                      │

                AI Providers

         (Speech + Evaluation Models)
```

Each service has a clearly defined responsibility.

---

# Environment Strategy

Maintain three environments.

## Development

Local development.

Safe testing.

Mock providers allowed.

---

## Staging

Mirror production.

Used before every release.

Real integrations.

Test database.

---

## Production

Customer traffic only.

No experimental features.

Protected credentials.

---

# Environment Variables

Configuration belongs in environment variables.

Examples

```text
NEXT_PUBLIC_SUPABASE_URL

NEXT_PUBLIC_SUPABASE_ANON_KEY

SUPABASE_SERVICE_ROLE_KEY

OPENAI_API_KEY

ANTHROPIC_API_KEY

DEEPGRAM_API_KEY

TRIGGER_SECRET_KEY

POSTHOG_API_KEY

SENTRY_DSN
```

Never hardcode secrets.

Never commit `.env` files.

---

# Configuration

Application behavior should be configurable.

Examples

Maximum upload size.

Maximum recording duration.

XP rewards.

Retry count.

AI provider.

Model selection.

Feature flags.

Configuration should live outside application code whenever practical.

---

# CI/CD Pipeline

Every change follows the same path.

```text
Developer

↓

Pull Request

↓

Automated Checks

↓

Code Review

↓

Merge

↓

Build

↓

Deploy to Staging

↓

Manual Verification

↓

Deploy to Production
```

No direct pushes to production.

---

# Required Automated Checks

Every deployment should verify:

TypeScript compilation.

Linting.

Formatting.

Unit tests.

Database migrations.

Build success.

Environment variables.

If any step fails,

deployment stops.

---

# Database Migrations

Schema changes must always use migration files.

Never modify production tables manually.

Every migration requires:

Version.

Description.

Rollback strategy.

Testing in staging.

---

# Feature Flags

All unfinished features remain behind feature flags.

Examples

Mock Interviews.

Conversation Mode.

Teams.

Organizations.

Premium.

Voice Coach.

Feature flags enable gradual rollout without separate deployments.

---

# Monitoring

Monitor both product health and infrastructure health.

Infrastructure

API latency.

Error rate.

Worker failures.

Queue size.

Database availability.

Storage usage.

AI provider latency.

Product

Workout completion.

Evaluation success.

Daily active users.

Retention.

Streak continuation.

These metrics should remain separate.

---

# Error Reporting

Unexpected failures should automatically create reports.

Capture:

Request ID.

Service.

Stack trace.

Environment.

Timestamp.

Never include:

Passwords.

Tokens.

Private transcripts.

Audio content.

---

# Logging

Use structured logs.

Every request should include:

Timestamp.

Request ID.

User ID (if authenticated).

Route.

Duration.

Status.

Logs should support debugging without exposing personal information.

---

# Health Endpoints

Expose lightweight endpoints for monitoring.

Examples

```text
/api/health

/api/health/database

/api/health/storage

/api/health/queue
```

Health checks should execute quickly.

Avoid expensive operations.

---

# Backup Strategy

Database

Daily automated backups.

Storage

Object versioning where supported.

Configuration

Version controlled.

Recovery procedures should be tested regularly.

Backups are useful only if restoration works.

---

# Disaster Recovery

The platform should survive:

AI provider outage.

Storage outage.

Database restart.

Background worker crash.

Network interruption.

Recovery priorities:

1. Preserve user recordings.
2. Preserve workout completion.
3. Resume evaluation automatically.
4. Notify users only when required.

Never lose completed user work.

---

# Cost Optimization

Optimize without sacrificing coaching quality.

Strategies

Queue expensive operations.

Compress recordings before upload.

Store structured AI outputs.

Cache static workout content.

Lazy-load history.

Archive inactive data.

Route lightweight tasks to lower-cost models.

Monitor AI cost per completed workout.

Cost should be observable.

---

# Scalability Strategy

Expected growth

1,000 Users

↓

10,000 Users

↓

100,000 Users

↓

1 Million Users

Scaling order

Increase compute.

Optimize queries.

Introduce caching.

Separate background workers.

Scale storage.

Introduce read replicas only when necessary.

Avoid premature infrastructure complexity.

---

# Security Operations

Rotate API keys regularly.

Review access permissions.

Audit storage policies.

Audit RLS policies.

Monitor suspicious authentication attempts.

Run dependency updates routinely.

Security is an ongoing process.

---

# Data Retention

Respect user ownership.

Allow users to:

Export their data.

Delete recordings.

Delete accounts.

Control reminder settings.

Historical analytics should be anonymized where possible.

---

# Production Checklist

Before every release confirm:

✓ Application builds successfully.

✓ Database migrations completed.

✓ Queue workers healthy.

✓ AI providers reachable.

✓ Storage available.

✓ Feature flags configured.

✓ Monitoring active.

✓ Error reporting active.

✓ Backups verified.

✓ Rollback plan prepared.

---

# Operational Principles

Prefer rollback over hotfixes.

Prefer reliability over speed.

Prefer observability over assumptions.

Prefer simple architecture over clever architecture.

Every operational decision should reduce future maintenance effort.

---

# Engineering Standards

Code should be:

Readable.

Testable.

Documented.

Versioned.

Replaceable.

Every service should be understandable without tribal knowledge.

---

# Definition of Production Ready

CommunicationGym is considered production ready when:

Users can authenticate reliably.

Daily workouts are assigned consistently.

Recordings upload safely.

Evaluations complete automatically.

Progress is never duplicated.

Failures recover gracefully.

Monitoring detects problems before users report them.

Deployment is repeatable.

Recovery is documented.

---

# Final Principle

Infrastructure should never become the product.

The backend exists to quietly support a simple, reliable coaching experience.

Users should remember how much their communication improved.

They should never have to think about the systems that made it possible.
