# BUILD_ORDER.md

> Version: 1.0

> Project Codename: CommunicationGym

---

# Purpose

This document defines the exact implementation sequence for CommunicationGym.

The objective is to build the smallest possible production-ready MVP while avoiding unnecessary rework.

Every phase depends on the successful completion of the previous phase.

Never skip phases.

Never implement future phases early.

---

# Implementation Philosophy

Build from the foundation upward.

Every new phase should make the previous phase more useful.

Do not build features because they are exciting.

Build them because another feature depends on them.

---

# Global Rules

Before every implementation phase:

1. Read README.md
2. Read IMPLEMENTATION_RULES.md
3. Read MVP_SCOPE.md
4. Read only the documentation relevant to the current phase.
5. Build only the requested phase.
6. Do not anticipate future features.
7. Stop after completing the requested phase.

---

# Phase 0 — Project Foundation

## Goal

Create a clean production-ready project foundation.

---

## Build

- Initialize Next.js
- Configure TypeScript
- Configure Tailwind
- Install shadcn/ui
- Configure ESLint
- Configure Prettier
- Configure folder structure
- Configure environment variables
- Connect GitHub
- Connect Vercel

---

## Do Not Build

Authentication

Pages

Database

Components

AI

---

## Documentation

README.md

IMPLEMENTATION_RULES.md

---

## Done When

Project runs locally without errors.

---

## Commit

```

chore: initialize project foundation

```

---

# Phase 1 — Supabase Foundation

## Goal

Connect the application to Supabase.

---

## Build

- Authentication setup
- Database connection
- Storage connection
- Environment validation

---

## Do Not Build

Dashboard

Recording

Workout

Leaderboard

AI

---

## Documentation

DATABASE.md

BACKEND_ARCHITECTURE.md

---

## Done When

Supabase connection is verified.

---

## Commit

```

feat: configure supabase foundation

```

---

# Phase 2 — Authentication

## Goal

Allow users to securely create an account.

---

## Build

- Google Login
- Session persistence
- Logout
- Protected routes
- User profile creation

---

## Do Not Build

Dashboard

Workouts

Recording

History

---

## Documentation

DATABASE.md

BACKEND_ARCHITECTURE.md

---

## Done When

Users can log in and return without losing their session.

---

## Commit

```

feat: implement authentication

```

---

# Phase 3 — Onboarding

## Goal

Understand why users joined.

---

## Build

- Welcome flow
- Goal selection
- Communication confidence
- User profile initialization

---

## Do Not Build

Daily Workout

Recording

AI

---

## Documentation

PRD.md

USER_FLOW.md

DATABASE.md

---

## Done When

New users complete onboarding successfully.

---

## Commit

```

feat: implement onboarding flow

```

---

# Phase 4 — Home Dashboard

## Goal

Give users a clear place to begin.

---

## Build

- Today's Daily Workout
- XP
- Streak
- Level
- Rank
- Navigation

---

## Do Not Build

Recording

History

Leaderboard

---

## Documentation

DESIGN_LANGUAGE.md

COMPONENT_LIBRARY.md

GAME_SYSTEM.md

---

## Done When

Dashboard displays personalized user data.

---

## Commit

```

feat: build home dashboard

```

---

# Phase 5 — Daily Workout

## Goal

Deliver one Daily Workout.

---

## Build

- Workout retrieval
- Workout display
- Reroll
- Timer

---

## Do Not Build

Recording

AI

---

## Documentation

PRD.md

GAME_SYSTEM.md

---

## Done When

Users can start today's workout.

---

## Commit

```

feat: implement daily workout

```

---

# Phase 6 — Recording

## Goal

Allow users to record their response.

---

## Build

- Microphone
- Timer
- Recording
- Playback
- Upload

---

## Do Not Build

Evaluation

History

---

## Documentation

BACKEND_ARCHITECTURE.md

DATABASE.md

---

## Done When

Users can successfully upload recordings.

---

## Commit

```

feat: implement recording pipeline

```

---

# Phase 7 — Coach Engine

## Goal

Generate AI coaching.

---

## Build

- Speech-to-text
- Metrics
- Evaluation
- Coach feedback

---

## Do Not Build

Communication DNA

Premium

Curriculum

---

## Documentation

AI_SYSTEM.md

DATABASE.md

---

## Done When

Users receive structured AI coaching.

---

## Commit

```

feat: integrate coach engine

```

---

# Phase 8 — Progress

## Goal

Track user improvement.

---

## Build

- XP
- Levels
- Rank
- Streak
- History

---

## Do Not Build

Achievements

Leaderboard

---

## Documentation

GAME_SYSTEM.md

DATABASE.md

---

## Done When

Progress updates correctly after every workout.

---

## Commit

```

feat: implement progression system

```

---

# Phase 9 — Leaderboard

## Goal

Introduce friendly competition.

---

## Build

- Weekly leaderboard
- User ranking
- Rank display

---

## Do Not Build

Friends

Teams

Schools

---

## Documentation

GAME_SYSTEM.md

DATABASE.md

---

## Done When

Weekly rankings update correctly.

---

## Commit

```

feat: implement leaderboard

```

---

# Phase 10 — MVP Polish

## Goal

Prepare for launch.

---

## Build

- Loading states
- Error handling
- Empty states
- Accessibility
- Responsive design
- Performance improvements
- Analytics
- Final QA

---

## Documentation

ANALYTICS.md

IMPLEMENTATION_RULES.md

---

## Done When

Application is production-ready.

---

## Commit

```

chore: prepare MVP for launch

```

---

# Definition of MVP Complete

The MVP is complete when a new user can:

1. Sign in.
2. Complete onboarding.
3. Receive today's workout.
4. Record their response.
5. Receive AI coaching.
6. Track progress.
7. Return tomorrow.

Nothing else is required for launch.

---

# Final Rule

Never ask an AI coding assistant to implement the entire application.

Always implement **exactly one phase** at a time.

Complete the phase.

Review it.

Commit it.

Then begin the next phase.

Small, verified iterations produce a more reliable product than large, speculative generations.
