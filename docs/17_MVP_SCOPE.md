# MVP_SCOPE.md

> Version: 1.0

> Project Codename: CommunicationGym

---

# Purpose

This document defines the exact scope of the Minimum Viable Product (MVP).

Its purpose is to prevent feature creep, reduce development time, minimize AI-generated implementation errors, and ensure CommunicationGym reaches real users as quickly as possible.

Every implementation decision should reference this document.

If a feature is not listed as part of the MVP, it should not be built.

---

# MVP Mission

Launch the smallest possible version of CommunicationGym that genuinely helps users become better communicators.

The MVP must prove that users are willing to:

- Show up daily.
- Complete speaking workouts.
- Receive AI coaching.
- Return consistently.

Nothing else matters until this is validated.

---

# Success Criteria

The MVP is considered successful when users can:

- Create an account.
- Complete onboarding.
- Receive a personalized Daily Workout.
- Record themselves speaking.
- Receive structured AI coaching.
- Track their improvement.
- Return the next day.

If users consistently complete Daily Workouts, the MVP has succeeded.

---

# Target Users

The MVP is designed for people who actively want to improve their communication.

Examples include:

- Students
- SDRs
- BDRs
- Sales professionals
- Job seekers
- Founders
- Public speakers
- College students
- Interview candidates
- English learners

Future audiences are intentionally excluded.

---

# Included Features

## Authentication

- Google Sign-In
- User profile creation
- Secure authentication
- Session persistence

---

## Onboarding

Collect only essential information.

- Name
- Primary goal
- Current communication confidence
- Preferred learning focus

No unnecessary questions.

---

## Home Dashboard

Displays:

- Today's Daily Workout
- Current streak
- XP
- Level
- Communication Rank
- Quick access to History

The dashboard should remain simple.

---

## Daily Workout

Users receive one personalized Daily Workout each day.

Users may reroll once.

Every workout includes:

- Prompt
- Category
- Suggested duration
- Primary skill

---

## Recording

Users record directly inside the application.

Requirements:

- Microphone permission
- Timer
- Recording controls
- Playback before submission

---

## AI Evaluation

Every completed recording receives:

- Overall summary
- Strengths
- Areas to improve
- Skill scores
- Tomorrow's focus

Responses should follow the coaching framework defined in AI_SYSTEM.md.

---

## History

Users can review previous workouts.

Each workout displays:

- Prompt
- Recording date
- Transcript
- Evaluation
- Skill scores

---

## Progress

Track:

- XP
- Level
- Rank
- Current streak
- Longest streak
- Workouts completed

---

## Leaderboard

Global weekly leaderboard only.

No friends.

No teams.

No schools.

No organizations.

Keep the first version simple.

---

## Profile

Users can:

- View profile
- Update display name
- Update avatar
- View communication statistics

---

# Explicitly Excluded

The following features are **not part of the MVP**.

Do not implement them.

## AI Conversation Mode

❌

---

## Mock Interviews

❌

---

## Sales Roleplays

❌

---

## Voice Conversations

❌

---

## Live AI Calls

❌

---

## Video Recording

❌

---

## Teacher Dashboard

❌

---

## Organization Dashboard

❌

---

## Teams

❌

---

## Friends

❌

---

## Campus Competitions

❌

---

## Certificates

❌

---

## Resume Review

❌

---

## Premium Subscription

❌

(Structure may exist internally, but no payment flow.)

---

## Mobile App

❌

---

## Offline Mode

❌

---

## Chat System

❌

---

## Notifications

❌

(In-app reminders may come later.)

---

## Multiple Languages

❌

English only for MVP.

---

# Free Experience

CommunicationGym follows a **Free Core** model.

The daily habit must always remain free.

Every user should be able to build the habit of becoming a better communicator without paying.

Free users receive:

- Daily Workout
- AI Coaching for the Daily Workout
- Workout History
- XP
- Levels
- Communication Rank
- Streaks
- Global Leaderboard
- Progress Tracking

The free experience should be valuable enough that users confidently recommend CommunicationGym to others.

---

# Premium Architecture

Premium is designed to accelerate improvement.

It should never lock the core habit behind a paywall.

Future premium features may include:

- Unlimited AI Practice
- Personalized Learning Paths
- Mock Interviews
- Sales Simulations
- Leadership Coaching
- Negotiation Practice
- Conversation Coach
- Advanced Progress Analytics
- AI Curriculum
- PDF Progress Reports

Premium expands learning.

Free builds the habit.

---

# Monetization Principle

CommunicationGym is habit-first.

The daily workout should never require payment.

Users should upgrade because they want more coaching,

not because they are prevented from practicing.

# Technical Constraints

The MVP should use:

- Next.js
- TypeScript
- Tailwind CSS
- shadcn/ui
- Supabase
- Trigger.dev
- OpenAI / Anthropic
- Speech-to-Text provider

Avoid introducing additional infrastructure unless absolutely necessary.

---

# Performance Targets

Landing page

< 2 seconds

Dashboard

< 2 seconds

Workout loading

< 1 second

Recording upload

< 10 seconds

AI evaluation

Target under 30 seconds

The application should always feel responsive.

---

# Design Constraints

Use only the approved:

- Design Language
- Design Tokens
- Component Library
- Motion System
- Copy Guide

Do not invent UI during implementation.

---

# Development Rule

During implementation ask one question before building any feature:

"Does this exist inside MVP_SCOPE.md?"

If the answer is "No",

do not build it.

---

# Launch Checklist

Before launch verify:

- Authentication works.
- Onboarding works.
- Daily Workout works.
- Recording works.
- AI evaluation works.
- History works.
- Progress updates correctly.
- Leaderboard updates correctly.
- Responsive layout verified.
- Accessibility reviewed.
- Error handling implemented.

Nothing else is required for launch.

---

# Definition of MVP Complete

CommunicationGym MVP is complete when a new user can:

1. Create an account.
2. Complete onboarding.
3. Receive today's workout.
4. Record themselves.
5. Receive AI coaching.
6. Return tomorrow and continue improving.

If these six steps work reliably,

the MVP is ready for real users.

---

# Final Principle

The purpose of the MVP is not to impress investors.

It is not to demonstrate AI.

It is not to showcase every idea.

The purpose of the MVP is to prove one hypothesis:

People will build a daily communication habit when coaching is simple, personal, and rewarding.

Everything else comes after that.
