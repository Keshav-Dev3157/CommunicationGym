# PRD.md

> **Product Requirements Document**
> **Version:** 0.2
> **Status:** Draft
> **Project Codename:** CommunicationGym *(Temporary name until branding is finalized.)*

---

# 1. Purpose

CommunicationGym is a habit-building platform that helps people become confident communicators through short daily speaking workouts.

The MVP is **not** designed to teach communication.

The MVP is designed to help people build the habit of practicing communication every day.

Every feature in this document exists to strengthen that habit.

---

# 2. MVP Goal

Validate one assumption:

> **Will users voluntarily return tomorrow to complete another communication workout?**

If users do not naturally build a habit of returning, the MVP has failed regardless of signups or downloads.

---

# 3. Primary User

CommunicationGym is built for **students of communication**.

This does not refer to academic students.

It refers to anyone intentionally improving how they communicate.

Examples include:

* College Students
* Job Seekers
* SDRs & BDRs
* Founders
* Professionals
* Content Creators
* Teachers
* Anyone committed to becoming a better communicator

The application should never feel exclusive to one profession.

---

# 4. Success Criteria

A first-time user should be able to:

1. Understand the product within 10 seconds.
2. Sign in quickly.
3. Complete onboarding in under 45 seconds.
4. Start today's workout within 60 seconds.
5. Complete today's workout.
6. Receive meaningful AI feedback.
7. Earn XP.
8. Feel rewarded.
9. Want to return tomorrow.

If any of these fail consistently, the MVP needs improvement.

---

# 5. Product Principles

The MVP must always be:

* Fast
* Beautiful
* Mobile-first
* Friendly
* Playful
* Rewarding
* Accessible
* Habit-forming

Every screen should have one clear primary action.

Users should never feel overwhelmed.

---

# 6. Core Product Loop

Every session follows the same experience.

```
Open App

↓

Spin Today's Workout

↓

Receive Personalized Workout

↓

Speak Naturally

↓

AI Evaluation

↓

Earn XP

↓

Increase Streak

↓

View Progress

↓

Come Back Tomorrow
```

Every feature should strengthen this loop.

Nothing should distract from it.

---

# 7. MVP Features

---

## Authentication

Users should be able to:

* Sign in using Google
* (Optional) Continue as Guest if implementation remains simple

Authentication should require minimal effort.

---

## Onboarding

The onboarding experience should collect just enough information to personalize Daily Workouts while remaining fast and enjoyable.

Questions include:

### What are you working towards?

* Interviews
* Placements
* Public Speaking
* Sales
* Confidence
* Leadership
* Networking
* General Communication

### How confident are you today?

* Beginner
* Intermediate
* Advanced

The onboarding should take less than **45 seconds**.

The collected information is used to personalize Daily Workouts and future recommendations.

---

## Home Screen

The home screen should immediately communicate progress.

Display:

* Current Streak
* Current Level
* Total XP
* Today's Workout CTA
* Motivational message
* Progress toward next level

Avoid unnecessary analytics or dashboard widgets.

The home screen should answer only one question:

> **"What should I do next?"**

---

## Daily Workout

The Daily Workout is permanently free.

It is the core growth engine of CommunicationGym.

Users receive one personalized communication workout every day.

Workouts are selected using onboarding preferences while maintaining enough variety to improve overall communication ability.

Examples include:

* Introduce yourself to your dream employer.
* Convince your friend to start a business.
* Explain AI to your grandparents.
* Tell the funniest story from your school life.
* Describe the biggest lesson you've learned.

The objective is spontaneous thinking and speaking.

Users should never read from a script.

---

## Daily Spin

Before each Daily Workout, users activate the **Daily Spin**.

The wheel reveals today's communication category.

Possible categories include:

* Storytelling
* Interviews
* Sales
* Networking
* Leadership
* Debate
* Creativity
* Confidence

The wheel should create anticipation and delight.

It must feel elegant and premium.

Never childish.

Never casino-like.

The wheel does **not** choose a completely random topic.

Instead, it reveals a personalized workout selected by the recommendation engine.

---

## Recording

Users record their spoken response.

Controls should remain extremely simple.

* Start Recording
* Stop Recording
* Replay Recording (Optional)

No editing.

No trimming.

No timeline.

No unnecessary complexity.

---

## AI Evaluation

After recording, AI evaluates the response.

The MVP provides:

* Overall Score
* Clarity
* Structure
* Vocabulary
* Pace
* Filler Words
* Communication Summary

The feedback also includes:

* Three strengths
* Three improvement areas
* One suggestion for tomorrow's workout

Feedback should always motivate improvement.

Never shame users.

The detailed evaluation framework will be defined in **AI.md**.

---

## Progress

Completing a workout rewards users with:

* XP
* Streak Progress
* Level Progress

Rewards are based on consistency rather than perfection.

The exact XP, level, and progression system will be defined in **GAME_SYSTEM.md**.

---

## Workout History

Users can revisit previous workouts.

Each workout should display:

* Date
* Workout Topic
* Overall Score
* XP Earned

The MVP intentionally avoids advanced analytics.

---

## Profile

Displays:

* Name
* Current Level
* Total XP
* Current Streak
* Longest Streak
* Total Workouts Completed

Simple.

Clean.

Motivating.

---

## Global Leaderboard

The MVP includes a single leaderboard.

**Weekly Global XP Leaderboard**

The leaderboard resets weekly to encourage fair competition and give new users a chance to participate.

Additional leaderboards will be introduced in future versions.

---

# 8. Premium Features (Not Included in MVP)

Premium expands the ways users can practice communication.

It does **not** remove limitations from the Daily Workout.

Potential premium experiences include:

* AI Mock Interviews
* Sales Roleplay
* Negotiation Simulator
* Presentation Coach
* Debate Coach
* Conversation Simulator
* Personalized Learning Paths
* Advanced Communication Analytics
* Custom Practice Sessions
* AI Communication Coach

These are intentionally excluded from the MVP.

---

# 9. Notifications

The MVP will not include:

* Push Notifications
* Email Reminders
* SMS Reminders

The product must first prove that users return naturally before introducing notification systems.

---

# 10. Visual Style

CommunicationGym should feel:

* Premium
* Friendly
* Calm
* Modern
* Motivating
* Delightful

Never:

* Childish
* Corporate
* Overly gamified
* Distracting

Animations should enhance the experience rather than slow it down.

---

# 11. Performance Targets

The application should feel instant.

Goals:

* Fast page loads
* Smooth animations
* Responsive interactions
* Minimal waiting

Users should never feel like the application is thinking.

---

# 12. Accessibility

CommunicationGym should be usable by everyone.

Design principles:

* Large touch targets
* Clear typography
* Strong contrast
* Simple language
* Minimal reading
* Mobile-first

If someone can comfortably use UPI, they should comfortably use CommunicationGym.

---

# 13. Non-Goals

The MVP is **not** trying to:

* Replace communication coaches
* Replace English learning platforms
* Replace speech therapy
* Replace ChatGPT
* Become another AI writing tool
* Become another course platform

The objective is to build a daily communication habit.

---

# 14. Definition of Done

The MVP is complete when a user can:

* Create an account
* Complete onboarding
* Spin today's workout
* Complete today's speaking workout
* Receive AI evaluation
* Earn XP
* Build a streak
* View workout history
* View profile
* Compete on the weekly leaderboard
* Return the next day for a new personalized workout

Without any external guidance.

---

# 15. Implementation Rules for Lovable

Lovable is responsible for implementation—not product design.

It must:

* Treat this PRD as the primary source of truth.
* Never invent new features.
* Never redesign the user experience.
* Never simplify user flows.
* Never introduce placeholder pages.
* Never add unnecessary settings.
* Never create additional dashboards.
* Ask before making architectural or product decisions.

If this document conflicts with another document:

Priority order:

1. PRD.md
2. USER_FLOW.md
3. DESIGN_SYSTEM.md
4. DECISIONS.md

When uncertain,

**Ask. Don't Assume.**
