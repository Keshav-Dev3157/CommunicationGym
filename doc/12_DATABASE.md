# DATABASE.md

> Version: 0.1
>
> Project Codename: CommunicationGym

---

# Purpose

The database is the long-term memory of CommunicationGym.

Every feature should store only the data required to create a better communication training experience.

The schema should support future expansion without requiring major redesigns.

Data integrity is more important than convenience.

---

# Architecture Philosophy

CommunicationGym follows a relational database model.

The database should prioritize:

* Simplicity
* Consistency
* Performance
* Scalability
* Security

Supabase PostgreSQL is the primary database.

Supabase Authentication manages authentication.

Supabase Storage stores media.

---

# Database Principles

## Principle 01

Normalize where practical.

Denormalize only for performance.

---

## Principle 02

Never duplicate business data.

Reference relationships instead.

---

## Principle 03

Soft-delete wherever possible.

Avoid permanent deletion of user-generated content.

---

## Principle 04

Every table includes:

* id
* created_at
* updated_at

unless explicitly unnecessary.

---

## Principle 05

UUIDs should be used as primary keys.

Never expose sequential IDs publicly.

---

# Entity Relationship Overview

```text
User
│
├── Profile
├── Goals
├── Settings
├── Streak
├── XP Ledger
├── User Achievements
├── Workout Sessions
│       │
│       ├── Recording
│       ├── Transcript
│       ├── Coach Feedback
│       └── Skill Scores
│
└── Leaderboard Snapshot

Workout Categories
        │
        └── Workout Prompts
                │
                └── Daily Assignments
```

---

# Core Tables

---

# users

Purpose

Stores authenticated users.

Authentication handled by Supabase Auth.

---

Fields

| Field         | Type      |
| ------------- | --------- |
| id            | UUID      |
| email         | Text      |
| auth_provider | Text      |
| created_at    | Timestamp |
| updated_at    | Timestamp |

---

Relationship

One user owns one profile.

---

# profiles

Purpose

Stores public profile information.

---

Fields

| Field               | Type      |
| ------------------- | --------- |
| id                  | UUID      |
| user_id             | UUID      |
| first_name          | Text      |
| last_name           | Text      |
| avatar_url          | Text      |
| communication_level | Integer   |
| communication_rank  | Text      |
| current_xp          | Integer   |
| total_xp            | Integer   |
| current_streak      | Integer   |
| longest_streak      | Integer   |
| workouts_completed  | Integer   |
| preferred_theme     | Enum      |
| timezone            | Text      |
| onboarding_complete | Boolean   |
| created_at          | Timestamp |
| updated_at          | Timestamp |

---

Relationship

One profile belongs to one user.

---

# user_goals

Purpose

Stores onboarding selections.

Examples

Interview

Sales

Networking

Leadership

Confidence

---

Fields

| Field      | Type      |
| ---------- | --------- |
| id         | UUID      |
| user_id    | UUID      |
| goal       | Text      |
| priority   | Integer   |
| created_at | Timestamp |

A user may have multiple goals.

---

# workout_categories

Purpose

Master list of communication categories.

Examples

Storytelling

Interview

Leadership

Networking

Debate

Sales

Presentation

Confidence

Persuasion

---

Fields

| Field       | Type    |
| ----------- | ------- |
| id          | UUID    |
| name        | Text    |
| description | Text    |
| icon        | Text    |
| active      | Boolean |

---

# workout_prompts

Purpose

Stores every communication challenge.

---

Fields

| Field              | Type      |
| ------------------ | --------- |
| id                 | UUID      |
| category_id        | UUID      |
| title              | Text      |
| prompt             | Text      |
| difficulty         | Enum      |
| estimated_duration | Integer   |
| primary_skill      | Text      |
| active             | Boolean   |
| created_at         | Timestamp |

---

Relationship

One category

↓

Many prompts.

---

# daily_assignments

Purpose

Tracks which workout was assigned to which user on which day.

This prevents duplicate assignments.

Supports personalized recommendations.

---

Fields

| Field             | Type      |
| ----------------- | --------- |
| id                | UUID      |
| user_id           | UUID      |
| workout_prompt_id | UUID      |
| assignment_date   | Date      |
| completed         | Boolean   |
| reroll_used       | Boolean   |
| created_at        | Timestamp |

---

Rule

Only one active Daily Assignment per user per day.

---

# workout_sessions

Purpose

Stores every completed workout.

This becomes one of the most important tables.

---

Fields

| Field              | Type      |
| ------------------ | --------- |
| id                 | UUID      |
| user_id            | UUID      |
| assignment_id      | UUID      |
| recording_duration | Integer   |
| started_at         | Timestamp |
| completed_at       | Timestamp |
| upload_status      | Enum      |
| evaluation_status  | Enum      |
| created_at         | Timestamp |

---

Relationship

One Workout Session

↓

One Recording

↓

One Transcript

↓

One Coach Feedback

---

# recordings

Purpose

Stores metadata for recorded audio.

Audio files themselves live in Supabase Storage.

---

Fields

| Field              | Type      |
| ------------------ | --------- |
| id                 | UUID      |
| workout_session_id | UUID      |
| storage_path       | Text      |
| duration           | Integer   |
| file_size          | Integer   |
| mime_type          | Text      |
| uploaded_at        | Timestamp |

---

Storage Bucket

communication-recordings

Private.

Never public.

---

# transcripts

Purpose

Stores speech-to-text output.

---

Fields

| Field                  | Type      |
| ---------------------- | --------- |
| id                     | UUID      |
| workout_session_id     | UUID      |
| transcript             | Text      |
| language               | Text      |
| transcription_provider | Text      |
| confidence_score       | Decimal   |
| created_at             | Timestamp |

The transcript is immutable.

Corrections are stored separately in future versions.

---

# Relationships Summary

```text
User
│
├── Profile (1:1)

├── Goals (1:N)

├── Daily Assignments (1:N)

├── Workout Sessions (1:N)

│        │

│        ├── Recording (1:1)

│        ├── Transcript (1:1)

│        └── Coach Feedback (1:1)

└── XP Ledger (1:N)
```

---

# Index Recommendations

Create indexes on:

user_id

assignment_date

completed_at

category_id

evaluation_status

These fields will be queried frequently.

---

# Initial Constraints

One profile per user.

One Daily Assignment per calendar day.

One recording per workout session.

One transcript per workout session.

One coach feedback record per workout session.

Referential integrity should always be enforced.

---

# MVP Scope

The MVP implements only the tables required for:

Authentication

Onboarding

Daily Workout

Recording

Transcript

Coach Feedback

XP

Profile

History

Leaderboard

Future tables will be added without modifying these foundations.

---

# Steve Jobs Test

If the application grows from 1,000 users to 10 million users,

the structure should remain understandable.

If engineers struggle to explain the schema on a whiteboard,

it is too complicated.

Prefer clarity over cleverness.
# DATABASE.md

## Phase 2 — AI Data, Progression & Platform Services

---

# Philosophy

Every completed workout should improve two things:

1. The user.

2. The coaching system.

CommunicationGym should continuously learn what helps each user become a better communicator.

The database should support personalization from Day 1, even if advanced features are introduced later.

---

# coach_feedback

## Purpose

Stores the structured coaching response for each workout.

Never store only plain text.

Always store structured feedback so it can be reused, filtered and improved.

---

### Fields

| Field              | Type      |
| ------------------ | --------- |
| id                 | UUID      |
| workout_session_id | UUID      |
| overall_score      | Integer   |
| summary            | Text      |
| strengths          | JSONB     |
| improvements       | JSONB     |
| next_challenge     | Text      |
| ai_model           | Text      |
| prompt_version     | Text      |
| evaluation_time_ms | Integer   |
| created_at         | Timestamp |

---

### Example

```json
{
  "strengths":[
    "Clear structure",
    "Good storytelling",
    "Strong conclusion"
  ],
  "improvements":[
    "Slow your pace",
    "Reduce filler words",
    "Pause before key ideas"
  ]
}
```

Never store formatted markdown.

Always store structured JSON.

---

# skill_scores

## Purpose

Stores communication metrics for every workout.

These values power progress charts and future personalization.

---

### Fields

| Field              | Type             |
| ------------------ | ---------------- |
| id                 | UUID             |
| workout_session_id | UUID             |
| clarity            | Integer          |
| storytelling       | Integer          |
| vocabulary         | Integer          |
| speaking_pace      | Integer          |
| filler_words       | Integer          |
| confidence         | Integer (future) |
| persuasion         | Integer          |
| structure          | Integer          |
| pronunciation      | Integer (future) |
| created_at         | Timestamp        |

---

## Rule

Only store metrics that can actually be measured.

Never fabricate scores.

Unknown values remain NULL.

---

# user_skill_progress

## Purpose

Represents the user's long-term improvement.

Unlike skill_scores,

this table stores cumulative progress.

---

### Fields

| Field              | Type      |
| ------------------ | --------- |
| id                 | UUID      |
| user_id            | UUID      |
| skill              | Text      |
| current_score      | Decimal   |
| highest_score      | Decimal   |
| workouts_completed | Integer   |
| last_updated       | Timestamp |

---

Example

```text
Storytelling

82.4

Best

91.2

Workouts

37
```

This becomes the foundation for personalized coaching.

---

# xp_ledger

## Purpose

Stores every XP transaction.

Never directly edit total XP.

Always calculate from the ledger.

---

### Fields

| Field        | Type      |
| ------------ | --------- |
| id           | UUID      |
| user_id      | UUID      |
| source       | Enum      |
| amount       | Integer   |
| reference_id | UUID      |
| created_at   | Timestamp |

---

### Sources

Workout

Streak

Achievement

Promotion

Special Event

Admin

Future Bonus

---

Benefits

Auditability.

Fraud detection.

Easy rollback.

Analytics.

---

# achievements

Master list of achievements.

---

### Fields

| Field       | Type      |
| ----------- | --------- |
| id          | UUID      |
| code        | Text      |
| title       | Text      |
| description | Text      |
| category    | Enum      |
| icon        | Text      |
| hidden      | Boolean   |
| xp_reward   | Integer   |
| created_at  | Timestamp |

---

# user_achievements

Stores unlocked achievements.

---

### Fields

| Field          | Type      |
| -------------- | --------- |
| id             | UUID      |
| user_id        | UUID      |
| achievement_id | UUID      |
| unlocked_at    | Timestamp |

---

Never duplicate achievement definitions.

---

# streak_history

Purpose

Track every streak.

Not only the current one.

---

Fields

| Field        | Type    |
| ------------ | ------- |
| id           | UUID    |
| user_id      | UUID    |
| streak_start | Date    |
| streak_end   | Date    |
| length       | Integer |

Useful for analytics and future coaching.

---

# leaderboard_snapshots

Purpose

Weekly leaderboard archive.

Avoid recalculating historical rankings.

---

Fields

| Field      | Type    |
| ---------- | ------- |
| id         | UUID    |
| user_id    | UUID    |
| week_start | Date    |
| week_end   | Date    |
| weekly_xp  | Integer |
| league     | Text    |
| rank       | Integer |

Historical rankings become permanent.

---

# notifications

Purpose

Stores in-app notifications.

Push notifications can reference these records later.

---

Fields

| Field      | Type      |
| ---------- | --------- |
| id         | UUID      |
| user_id    | UUID      |
| title      | Text      |
| message    | Text      |
| type       | Enum      |
| read       | Boolean   |
| created_at | Timestamp |

---

# user_settings

Purpose

Application preferences.

---

Fields

| Field            | Type    |
| ---------------- | ------- |
| id               | UUID    |
| user_id          | UUID    |
| theme            | Enum    |
| timezone         | Text    |
| language         | Text    |
| reminder_enabled | Boolean |
| reminder_time    | Time    |
| analytics_opt_in | Boolean |
| marketing_opt_in | Boolean |

Future settings belong here.

Never overload the profile table.

---

# ai_memory

## Purpose

This is one of the most important future tables.

It stores persistent coaching knowledge.

Not conversation history.

Learning history.

---

Example

Instead of

"You used filler words today."

Store

```text
User consistently improves after receiving pace-related coaching.

Preferred workout length

2 minutes.

Weakest area

Storytelling.

Strongest area

Vocabulary.
```

---

### Fields

| Field        | Type      |
| ------------ | --------- |
| id           | UUID      |
| user_id      | UUID      |
| memory_key   | Text      |
| memory_value | JSONB     |
| confidence   | Decimal   |
| updated_at   | Timestamp |

Future AI coaching should reference this table before generating feedback.

---

# Storage Buckets

communication-recordings

Private

Original audio.

---

avatars

Public

Optimized profile images.

---

achievement-assets

Public

Badge images.

---

generated-share-cards

Public

Temporary.

Auto-delete after 30 days.

---

future-resumes

Private

Mock interview uploads.

---

# Row Level Security

Every user can:

Read

Own records.

Insert

Own records.

Update

Own profile.

Delete

Never directly delete historical progress.

Admins receive elevated policies.

Service role bypasses RLS only where required.

---

# Foreign Key Rules

Every relationship should enforce referential integrity.

Never leave orphan records.

Deleting a user should:

Soft-delete profile.

Retain anonymized analytics.

Delete private recordings after the retention period.

---

# Audit Strategy

Important actions should create immutable logs.

Examples

Level Up

Achievement Unlock

Admin Changes

Premium Purchase

Account Deletion

Future compliance becomes much easier.

---

# Data Retention

Audio

User controlled.

Transcript

Retained unless deleted.

Coach Feedback

Retained.

XP History

Permanent.

Achievements

Permanent.

Leaderboard Snapshots

Permanent.

Analytics

Aggregated after retention window.

---

# Privacy

Users own their recordings.

Users can export:

Profile

History

Feedback

Transcript

Audio

Support GDPR-style portability from the beginning.

---

# MVP Scope

Required

Coach Feedback

Skill Scores

XP Ledger

Achievements

Leaderboard

Settings

Storage

Optional after launch

AI Memory

Notifications

Audit Logs

Reminder Preferences

---

# Database Review Checklist

Before adding a new table ask:

Can an existing table support this?

Can this become a relationship instead?

Will this scale to ten million users?

Does this expose unnecessary personal data?

If a table fails these questions,

redesign it.

---

# Final Principle

CommunicationGym is building more than a database.

It is building a lifelong record of communication growth.

Every table should contribute to helping users become more confident communicators.

The database exists to remember progress,

not just store information.
# DATABASE.md

## Phase 3 — Platform Architecture, Scaling & Future Foundation

---

# Platform Philosophy

CommunicationGym is not a CRUD application.

It is an event-driven learning platform.

Every meaningful user action produces an event.

Those events update user progress, AI memory, analytics and future recommendations.

The database should become the source of truth for the entire platform.

---

# Communication Profile

## Purpose

The Communication Profile represents the user's long-term communication identity.

Unlike workout sessions, which are individual events, the Communication Profile is continuously updated over time.

It should answer questions like:

* What kind of communicator is this user becoming?
* Which skills are improving?
* Which weaknesses persist?
* Which coaching style works best?
* What topics produce the strongest engagement?

This profile should evolve after every completed workout.

---

## Suggested Fields

| Field                    | Type      |
| ------------------------ | --------- |
| id                       | UUID      |
| user_id                  | UUID      |
| communication_rank       | Text      |
| current_level            | Integer   |
| strongest_skill          | Text      |
| weakest_skill            | Text      |
| preferred_categories     | JSONB     |
| learning_style           | Text      |
| average_session_duration | Decimal   |
| average_score            | Decimal   |
| growth_trend             | Decimal   |
| coach_style              | Text      |
| last_evaluated_at        | Timestamp |

This table becomes the foundation for personalized coaching.

---

# Communication Timeline

## Purpose

Stores snapshots of communication growth.

Rather than recalculating historical trends, the application records periodic summaries.

Example:

Day 1

↓

Clarity 42

↓

Day 30

↓

Clarity 61

↓

Day 90

↓

Clarity 79

This enables visual progress charts and longitudinal analysis.

---

# Evaluation Reports

Rename backend table from **coach_feedback** to **evaluation_reports**.

Reason:

"Coach Feedback" is the user-facing concept.

"Evaluation Report" is the technical representation.

One report contains:

* Raw metrics
* Structured scores
* Generated coaching
* Model metadata
* Processing information

The UI transforms the report into a coaching experience.

---

# AI Versioning

Every evaluation must remain reproducible.

Never overwrite historical AI results.

Store:

| Field                  | Description               |
| ---------------------- | ------------------------- |
| ai_provider            | OpenAI, Anthropic, etc.   |
| model_name             | GPT-5.5, Claude, etc.     |
| prompt_version         | Internal prompt version   |
| evaluation_schema      | JSON schema version       |
| scoring_version        | Scoring algorithm version |
| speech_metrics_version | Speech analysis version   |

Future improvements should create new reports, not mutate history.

---

# Evaluation Pipeline

The evaluation process should be asynchronous.

```text id="cg-db-pipeline"
Workout Complete

↓

Recording Uploaded

↓

Create Evaluation Job

↓

Speech-to-Text

↓

Speech Metrics

↓

Prompt Builder

↓

LLM Evaluation

↓

Schema Validation

↓

Evaluation Report

↓

Skill Progress Update

↓

Communication Profile Update

↓

XP Ledger Update

↓

Achievement Check

↓

Leaderboard Update

↓

Notification

↓

User Sees Coach Feedback
```

No single API request should perform the entire pipeline.

---

# Background Jobs

Long-running work should execute through jobs.

Suggested jobs:

* transcription_job
* speech_metrics_job
* ai_evaluation_job
* profile_update_job
* leaderboard_refresh_job
* achievement_processor
* notification_dispatcher
* analytics_export_job

Jobs should be idempotent.

Running a job twice should not duplicate progress.

---

# Event Architecture

Every important action emits an event.

Examples:

```text
USER_REGISTERED

ONBOARDING_COMPLETED

DAILY_WORKOUT_ASSIGNED

WORKOUT_STARTED

WORKOUT_COMPLETED

RECORDING_UPLOADED

TRANSCRIPT_CREATED

AI_EVALUATION_COMPLETED

LEVEL_UP

ACHIEVEMENT_UNLOCKED

STREAK_UPDATED

LEADERBOARD_UPDATED
```

Future systems should react to events rather than tightly coupled database updates.

---

# Caching Strategy

Frequently accessed data should be cached.

Examples:

* User profile
* Current streak
* Current XP
* Today's workout
* Leaderboard (weekly)
* Achievement definitions

Do not cache:

* Evaluation reports during processing
* Upload status
* User settings being edited

---

# Search Strategy

Prepare for future search capabilities.

Users should eventually search:

* Previous transcripts
* Coach feedback
* Workout prompts
* Categories

Use PostgreSQL Full Text Search initially.

Vector search may be added later for semantic search.

---

# Storage Strategy

Storage buckets should remain organized.

```text
communication-recordings/

    user-id/

        year/

            month/

                recording.wav
```

Future buckets:

* transcript-exports
* report-pdfs
* share-cards
* avatars
* achievement-assets

Never mix unrelated assets.

---

# Security Model

Security is enforced at multiple layers.

Authentication

↓

Authorization

↓

Row Level Security

↓

Service Role

↓

Storage Policies

↓

Audit Logs

Every layer should assume the previous layer may fail.

---

# Data Ownership

Users own:

* Audio recordings
* Transcripts
* Evaluation reports
* Progress history

CommunicationGym owns:

* Workout templates
* Achievement definitions
* Coaching framework
* AI prompt architecture

Users must always be able to export their personal data.

---

# Privacy Principles

Collect only information that improves coaching.

Never collect unnecessary personal information.

Never retain recordings longer than user preference.

Never expose private progress publicly without explicit consent.

Privacy should be the default.

---

# Scaling Strategy

Design for growth.

Target milestones:

* 1,000 users
* 10,000 users
* 100,000 users
* 1 million users
* 10 million users

Scaling should require infrastructure changes, not schema redesign.

---

# Cost Optimization

AI is the most expensive subsystem.

Optimize by:

* Queue-based processing
* Structured JSON outputs
* Prompt version reuse
* Cached workout templates
* Background processing
* Lazy loading reports

Never call expensive models synchronously from the UI.

---

# Backup Strategy

Database

Daily backups.

Storage

Object versioning where available.

Critical configuration

Stored in version control.

Backups should be periodically tested through restoration drills.

---

# Disaster Recovery

Prepare for:

* Storage outage
* AI provider outage
* Database outage
* Queue failure

Users should never lose completed workouts because a downstream service failed.

Persist recordings before evaluation begins.

---

# Migration Rules

Every schema change requires:

* Version number
* Migration script
* Rollback strategy
* Documentation update

Never modify production tables manually.

All changes should be reproducible.

---

# Feature Flags

Future features should be gated.

Examples:

* Mock Interviews
* Live Conversation Coach
* Team Workspaces
* Campus Competitions
* Premium Practice
* AI Memory v2

Release gradually.

Never couple unfinished features to production code.

---

# Engineering Principles

When designing new tables ask:

1. Is this data truly necessary?
2. Does an existing table already represent it?
3. Will this scale to millions of records?
4. Is it easy to explain?
5. Is it easy to migrate?
6. Can it be secured with Row Level Security?
7. Does it help users become better communicators?

If the answer to the last question is "no," reconsider whether the data belongs in the platform.

---

# Architecture Review Checklist

Before every major release verify:

* Referential integrity
* RLS policies
* Storage policies
* Index coverage
* Query performance
* Backup success
* Migration rollback
* AI pipeline health
* Event processing health
* Data retention compliance

---

# Database Vision

CommunicationGym is building more than a database.

It is building the lifelong communication history of every user.

Years from now, a user should be able to open their profile and see:

* Their first recorded workout.
* How their speaking evolved.
* Which skills improved.
* Which coaching methods helped most.
* How consistent practice transformed their confidence.

The database is not simply a persistence layer.

It is the foundation of a personal communication journey that may span years.

Every table, relationship and event should exist to support that mission.
