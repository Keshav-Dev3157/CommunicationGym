# USER_FLOW.md

> Version: 0.1
>
> Project Codename: CommunicationGym

---

# Introduction

This document defines every user interaction inside CommunicationGym.

It is the primary UX specification for the MVP.

Its purpose is to remove ambiguity before implementation begins.

Developers should never invent user flows.

Designers should never guess interactions.

Every screen exists to strengthen one objective:

> Build a daily communication habit.

Whenever implementation conflicts with this document,

this document wins.

---

# User Journey Overview

Every new user should experience the following emotional journey.

```text
Curiosity

↓

Interest

↓

Excitement

↓

Commitment

↓

Focus

↓

Achievement

↓

Reflection

↓

Motivation

↓

Return Tomorrow
```

Every screen contributes to this emotional transition.

If a screen interrupts this journey,

it should be redesigned.

---

# FLOW 01

# Landing Experience

---

## Purpose

Introduce CommunicationGym in under ten seconds.

The landing page should not attempt to explain every feature.

Its only responsibility is to make visitors curious enough to try today's workout.

Users should experience the product before being asked to create an account.

---

## User Goal

"I want to see what this product actually does."

---

## Business Goal

Increase visitor-to-signup conversion by allowing users to interact with the product before authentication.

---

## Emotional Goal

The visitor should think:

> "That actually looks fun."

Not

> "Another AI SaaS."

---

## Entry Conditions

User visits:

communicationgym.com

No authentication required.

Landing page should load immediately.

---

# Hero Section

The first screen occupies the entire viewport.

No scrolling required.

Everything important should be visible immediately.

---

## Hero Layout

Top Navigation

↓

Brand Logo

↓

Theme Toggle

↓

Hero Headline

↓

Hero Subheading

↓

Primary CTA

↓

Daily Spin Preview

↓

Social Proof (future)

---

## Navigation

Minimal.

Logo on the left.

Navigation links on the right.

Only:

Features

About

Leaderboard

Login

No Pricing page.

No Blog.

No unnecessary navigation.

The objective is reducing decisions.

---

# Hero Headline

Large.

Bold.

Readable.

Example direction:

> Become a Better Communicator.

Second line:

> Five Minutes a Day.

No buzzwords.

No AI mention.

No technical language.

The message should immediately communicate transformation.

---

# Hero Supporting Text

One concise paragraph.

Example direction:

Practice speaking every day.

Receive instant coaching.

Build confidence one workout at a time.

The copy should focus on outcomes,

not features.

---

# Primary CTA

Large.

Centered.

Highest visual priority.

Text:

**Spin Today's Workout**

Not

Get Started

Not

Try Now

The CTA should communicate curiosity.

---

# Secondary CTA

Smaller.

Below primary.

Text:

See How It Works

This should smoothly scroll to a future section.

No popup.

---

# Daily Spin Preview

The Daily Spin should already be visible on the landing page.

It should feel alive.

Subtle breathing animation.

Very slow.

No aggressive movement.

It should invite interaction without demanding attention.

---

# Daily Spin Interaction

When the user presses

Spin Today's Workout

The wheel expands slightly.

Soft glow appears.

Wheel begins rotating.

Animation duration:

Approximately 1.5 seconds.

Rotation should feel weighted.

Not random.

Not slot-machine style.

The wheel should feel engineered,

not playful.

---

# Reveal Animation

The wheel slows naturally.

Category card fades in.

Example:

━━━━━━━━━━━━━━

Today's Workout

Storytelling

━━━━━━━━━━━━━━

The topic fades in.

Example

Tell us about a moment that changed your life.

Estimated Time

2 Minutes

Difficulty

Beginner

Primary Skill

Storytelling

━━━━━━━━━━━━━━

The user should immediately imagine answering the question.

---

# Transition to Signup

After the workout is revealed,

display:

━━━━━━━━━━━━━━

Ready to begin?

Create your free account.

Complete today's workout.

Receive your first coaching report.

━━━━━━━━━━━━━━

Button

Continue with Google

This transition should feel natural.

The signup request happens only after value has been demonstrated.

---

# Background Design

Use generous whitespace.

Avoid visual clutter.

Soft gradients are acceptable.

Heavy gradients are not.

The wheel remains the visual centerpiece.

Everything else supports it.

---

# Typography

Large headings.

Comfortable spacing.

Readable paragraphs.

The page should feel calm.

Never crowded.

---

# Empty States

None.

The landing page should always feel alive.

---

# Loading States

If today's workout is loading,

show:

Preparing today's workout...

Never display a spinner alone.

Every loading state should communicate progress.

---

# Error States

If the Daily Spin fails to load,

replace it with:

Unable to load today's workout.

Please try again.

Provide:

Retry button.

Never expose technical errors.

---

# Animations

Hero content fades upward.

Navigation appears first.

Headline second.

CTA third.

Wheel last.

Every animation should feel sequential.

Never everything at once.

Maximum animation duration:

300 milliseconds.

Exception:

Wheel spin.

Approximately 1.5 seconds.

---

# Accessibility

Entire landing page should be keyboard navigable.

Buttons should have clear focus states.

Text should maintain AA contrast.

Touch targets minimum:

48px.

---

# Exit Paths

User chooses one of three actions.

1.

Spin Today's Workout

↓

Google Login

↓

Onboarding

2.

Login

↓

Dashboard

3.

Leave

No modal should attempt to stop them.

---

# Acceptance Criteria

A first-time visitor should:

Understand the product within ten seconds.

Interact with the Daily Spin without confusion.

Feel curious about today's workout.

Reach Google Login only after experiencing value.

Never feel overwhelmed.

Never feel sold to.

The landing page succeeds if users think:

> "I want to know how well I'd do."

Instead of:

> "I should probably sign up."

---

# Steve Jobs Test

Remove every illustration.

Remove every animation.

Remove every gradient.

Remove every icon.

If the page still clearly communicates its purpose,

the design succeeds.

If it relies on decoration,

it must be redesigned.


# FLOW 02

# Authentication & Onboarding

---

# Purpose

Authentication and onboarding should feel like joining a gym, not creating an account.

The user has already experienced the value of the product by spinning the Daily Workout on the landing page.

At this point they have mentally committed.

Our responsibility is to remove every remaining obstacle between curiosity and their first workout.

The entire authentication and onboarding experience should take less than **60 seconds**.

The user should never feel like they are filling out forms.

Instead, they should feel like their communication coach is getting to know them.

---

# User Goal

"I want to start my first workout."

---

# Business Goal

* Create an authenticated user.
* Collect enough information to personalize Daily Workouts.
* Start the first workout immediately after onboarding.
* Build emotional commitment before the first session.

---

# Emotional Journey

```text
Curiosity

↓

Commitment

↓

Personalization

↓

Excitement

↓

"My first workout is ready."
```

---

# Entry Condition

User has:

* Clicked **Continue with Google** after previewing the Daily Workout.

---

# Screen 1 — Authentication

---

## Purpose

Authenticate the user with the least possible friction.

---

## Layout

Minimal page.

Centered content.

CommunicationGym logo.

Short welcome message.

Google Sign-In button.

Privacy note.

Nothing else.

---

## Headline

Welcome to CommunicationGym.

---

## Supporting Text

Let's save your progress so your communication journey grows with you.

---

## Primary CTA

Continue with Google

---

## Secondary Text

No credit card required.

Daily Workouts are always free.

---

## Interaction

Clicking Continue with Google immediately opens the Google authentication flow.

No additional forms.

No username.

No password.

---

## Success State

User account is created.

User profile is initialized.

User is automatically redirected into onboarding.

---

## Error State

Authentication failed.

Please try again.

Retry button only.

No technical jargon.

---

# Screen 2 — Welcome

Authentication completes.

The screen transitions naturally.

No page refresh feeling.

---

## Layout

Centered.

Friendly.

Minimal.

---

## Copy

🏋️ Welcome, {First Name}

We're excited to train with you.

Before we begin,

let's personalize your workouts.

Button:

Let's Begin →

---

## Animation

The user's first name fades in after login.

Button gently appears afterwards.

---

# Screen 3 — Goal Selection

---

## Purpose

Understand why the user wants to improve.

This decision personalizes future workouts.

---

## Headline

What are you training for?

---

## Layout

Large cards.

One question only.

Cards should feel tappable.

Examples:

💼 Job Interviews

🎤 Public Speaking

🤝 Networking

📈 Sales

🚀 Startup Pitches

💬 Everyday Confidence

🎓 College Placements

✨ General Improvement

Users may choose multiple goals.

---

## Interaction

Selecting a card creates immediate visual feedback.

Selected cards slightly elevate.

Soft glow.

Small checkmark.

Never use aggressive colors.

---

## Primary CTA

Continue

Disabled until at least one goal is selected.

---

# Screen 4 — Confidence Level

---

## Purpose

Estimate the user's starting point.

This determines workout difficulty.

---

## Headline

How confident do you feel today?

---

## Options

🌱 Beginner

"I often struggle expressing myself."

⚡ Intermediate

"I'm comfortable but want to improve."

🏆 Advanced

"I already communicate well and want mastery."

---

## UX Rule

No option should feel embarrassing.

Avoid words like:

Weak

Poor

Bad

---

# Screen 5 — Commitment Screen

This screen creates emotional investment.

---

## Layout

Minimal.

Large illustration space.

Centered copy.

---

## Copy

Communication improves through consistency.

Not perfection.

Your goal is simple.

Show up.

Five minutes.

Every day.

---

Button

I'm Ready

---

# Screen 6 — First Workout

This screen replaces the typical

"Onboarding Complete"

screen.

We never congratulate users for answering questions.

We congratulate them for beginning.

---

## Layout

Large.

Minimal.

Beautiful.

---

## Copy

🏋️

Your first workout is ready.

Take a deep breath.

Let's see today's challenge.

---

## Primary CTA

Spin Today's Workout

---

## Interaction

Pressing the button immediately transitions into the Daily Spin experience.

The user should never feel onboarding has ended.

Instead,

they should feel training has begun.

---

# Progress Indicator

Throughout onboarding,

display a subtle progress indicator.

Example:

● ● ○ ○

Never use percentages.

Never display

Step 2 of 5.

Dots feel lighter.

---

# Animation Principles

Every question enters individually.

Nothing appears all at once.

Transitions:

250–300ms.

Cards slightly lift on hover.

Selected options gently scale.

No dramatic movement.

---

# Accessibility

Entire onboarding should be usable using keyboard only.

Touch targets minimum 48px.

Readable typography.

High contrast.

Clear focus states.

---

# Empty States

None.

Every screen should always provide a next action.

---

# Error Handling

Network interruption:

"We're having trouble saving your progress."

Retry.

Authentication expires:

Automatically restart authentication.

Lost internet:

Detect offline state.

Allow retry.

Never lose already selected answers.

---

# Exit Paths

User may:

Complete onboarding.

Return to Landing Page.

Close the browser.

If onboarding is incomplete,

resume from the last completed step after login.

---

# Acceptance Criteria

The onboarding succeeds if a first-time user can:

* Complete authentication in under 20 seconds.
* Finish onboarding in under 60 seconds.
* Understand why questions are being asked.
* Feel personally welcomed.
* Reach their first workout without confusion.
* Never encounter unnecessary forms.
* Feel excited rather than exhausted.

---

# Steve Jobs Test

Remove all icons.

Remove animations.

Remove illustrations.

Does the onboarding still feel obvious?

Can someone complete it without instructions?

If not,

simplify further.

The best onboarding is one users barely remember because it felt effortless.


# FLOW 03

# Training Hub (Home Dashboard)

---

# Purpose

The Training Hub is the heart of CommunicationGym.

Users should immediately understand three things:

* Where they are in their journey.
* What they should do next.
* How much they've improved.

This is not a dashboard.

This is today's training room.

The screen should encourage action, not browsing.

---

# User Goal

"I'm here to complete today's workout."

---

# Business Goal

Increase Daily Active Users.

Maximize workout completion.

Increase streak retention.

Reduce decision fatigue.

---

# Emotional Goal

Users should feel:

"I'm making progress."

Not:

"I have to figure out what to do."

---

# Entry Conditions

The user has:

* Logged in.
* Completed onboarding.
* Finished at least one workout OR is returning for another day.

---

# Screen Hierarchy

The visual hierarchy should always follow this order.

```text
1. Today's Workout

2. Streak

3. XP Progress

4. Weekly Rank

5. Previous Progress

Everything else comes afterwards.
```

Today's workout should dominate the page.

Nothing should compete with it.

---

# Layout

The page should be vertically structured.

```
Header

↓

Welcome Message

↓

Today's Workout Card

↓

Progress Summary

↓

Weekly Leaderboard Preview

↓

Previous Workout Preview

↓

Bottom Navigation (Mobile)
```

No sidebars.

No complicated menus.

---

# Header

---

## Left

CommunicationGym Logo

---

## Right

Profile Picture

Notification Icon (Reserved for Future)

Theme Toggle (Optional)

---

# Welcome Message

The welcome should feel human.

Rotate messages.

Examples:

Welcome back, Keshav.

Ready for today's workout?

━━━━━━━━━━━━━━

Consistency beats talent.

Let's train.

━━━━━━━━━━━━━━

One conversation can change your life.

Let's practice.

━━━━━━━━━━━━━━

Don't break your streak.

Your future self is waiting.

Never repeat the same message too frequently.

---

# Workout Card (Most Important Component)

This is the largest card on the screen.

It should immediately attract attention.

---

## Contents

Today's Workout

Today's Category

Estimated Time

Difficulty

Skill Focus

Current Streak

---

Example

```
Today's Workout

Storytelling

Explain a mistake that taught you something valuable.

⏱ 2 Minutes

🎯 Confidence + Storytelling

🔥 7 Day Streak
```

---

## Primary CTA

Large button.

Centered.

Highest visual priority.

Text:

🎡 Spin Today's Workout

---

Interaction

The card slightly expands when pressed.

The background subtly changes.

The wheel appears full screen.

---

# Progress Card

Purpose:

Remind users that progress exists.

Without overwhelming them.

---

Display

Current Level

XP

XP until next level

Progress Bar

Example

```
Communication Level

Level 7

1,420 XP

280 XP until Level 8
```

The progress bar should animate smoothly.

---

# Weekly Progress

Small section.

Not dominant.

Displays

Current Weekly Rank

Current League

XP This Week

Example

```
Global Rank

#482

Silver League

740 XP
```

Clicking opens Leaderboards.

---

# Previous Workout

Users should remember yesterday.

Display

Yesterday's Topic

Score

Coach's Comment

Example

```
Yesterday

Convince someone to start reading books.

91/100

Coach:

Excellent structure.

Try slowing down slightly.
```

Tapping opens full report.

---

# Daily Motivation

Below previous workout.

One quote.

Examples

━━━━━━━━━━━━━━

The person you become

is shaped by the conversations

you practice today.

━━━━━━━━━━━━━━

Confidence grows

every time you choose

to speak.

━━━━━━━━━━━━━━

Your future interview

starts with today's workout.

Keep these authentic.

Never use generic motivational clichés.

---

# Bottom Navigation

Maximum four items.

Home

History

Leaderboard

Profile

Nothing else.

Future tabs remain hidden until needed.

---

# Empty State (Brand-New User)

A brand-new user should never see an empty dashboard.

Instead:

```
Welcome.

Today's workout is waiting.

Press below to begin.

[ Spin Today's Workout ]
```

---

# Returning User

If today's workout is already complete.

Replace the main card with

```
🏋️ Workout Complete

Come back tomorrow

to continue your streak.

```

Secondary Actions

Review Feedback

View Leaderboard

Browse History

Do NOT allow unlimited Daily Workouts.

The daily habit is more important than binge usage.

---

# Loading States

Never use skeleton screens for the Workout Card.

Instead.

Display

Preparing today's workout...

This should take less than one second whenever possible.

Other cards may use subtle skeleton placeholders.

---

# Error States

If today's workout cannot load

Display

"We couldn't prepare today's workout."

Primary Button

Try Again

Secondary

Continue Offline (Future)

Never expose technical messages.

---

# Micro Animations

XP counter counts upward.

Progress bar fills smoothly.

Workout card gently floats (very subtle).

Buttons compress slightly when tapped.

Cards lift on hover (desktop).

Transitions remain below 300ms.

---

# Accessibility

Every section should be keyboard navigable.

Readable on small devices.

Minimum touch target 48px.

Screen reader labels for every interactive element.

Animations should respect reduced-motion settings.

---

# Exit Paths

Users may

Start Today's Workout

↓

History

↓

Leaderboard

↓

Profile

↓

Logout

No dead ends.

Every screen should lead somewhere meaningful.

---

# Acceptance Criteria

A returning user should understand the entire screen within five seconds.

Without reading documentation they should know:

* What today's task is.
* Their current progress.
* Their streak.
* Their next action.

If users spend time searching for the correct button,

the screen has failed.

---

# Steve Jobs Test

Hide the colors.

Hide the icons.

Hide the illustrations.

Can someone still understand exactly what this page wants them to do?

If yes,

the design succeeds.

If not,

remove complexity until it becomes obvious.

---

# Future Hooks (Not for MVP)

Reserved areas may later support:

* Friends Activity
* Coach Recommendations
* Weekly Challenges
* Campus Competitions
* Team Leagues
* Premium Workout Suggestions

These should not appear in the MVP UI but the layout should allow graceful expansion without redesigning the entire screen.

# FLOW 04

# Daily Workout & Recording Session

---

# Purpose

This flow represents the core product experience.

Every interaction should help the user focus on speaking—not operating the application.

The product should disappear into the background.

The user's attention belongs entirely on today's communication challenge.

---

# User Goal

"I want to complete today's workout."

---

# Business Goal

Maximize workout completion.

Create a satisfying daily ritual.

Collect high-quality recordings for meaningful AI feedback.

---

# Emotional Goal

The user should move through:

Curiosity

↓

Preparation

↓

Focus

↓

Flow

↓

Accomplishment

---

# Entry Conditions

User is on the Training Hub.

Today's workout has not yet been completed.

---

# Screen 1 — Daily Spin

---

## Purpose

Create anticipation before revealing today's workout.

---

## Layout

Full-screen overlay.

Background softly blurred.

The wheel is centered and occupies approximately 70% of the available width on mobile.

The rest of the interface fades away.

Nothing should distract from the interaction.

---

## Components

* Communication category wheel
* Soft ambient glow
* Category labels
* Spin animation
* Subtle haptic cue (future mobile)
* Skip animation disabled

---

## Interaction

User presses:

**Spin Today's Workout**

The wheel immediately responds.

The spin lasts approximately 1.5 seconds.

The movement should feel weighted and premium.

Avoid casino-style randomness.

The final category is selected from the personalized recommendation engine, not by the wheel itself.

The wheel is a reveal mechanism, not the decision-maker.

---

# Screen 2 — Workout Reveal

---

## Purpose

Clearly explain today's communication exercise before recording begins.

---

## Layout

Large workout card.

Centered.

Plenty of whitespace.

---

## Display

Category

Workout title

Prompt

Recommended duration

Primary communication skill

Difficulty

---

### Example

**Storytelling**

**Describe a moment that completely changed your perspective.**

⏱ Recommended Time

2 Minutes

🎯 Skill

Storytelling

Difficulty

Intermediate

---

## Primary CTA

**I'm Ready**

---

## Secondary CTA

Spin Again

Only one free re-spin per day.

The second workout replaces the first.

This prevents users from endlessly searching for "easy" topics.

---

# Screen 3 — Thinking Time

---

## Purpose

Allow users to mentally organize their thoughts before speaking.

Communication improves when people think before talking.

---

## Layout

Minimal.

Timer centered.

Workout prompt remains visible.

Everything else disappears.

---

## Default Time

30 seconds.

Users may:

* Skip immediately.
* Wait for timer.
* Extend by 30 seconds once.

Maximum preparation:

60 seconds.

---

## Copy

Take a moment.

Think.

Structure your thoughts.

You don't need perfect words.

You just need to begin.

---

## CTA

Start Workout Now

---

# Screen 4 — Recording Session

---

## Purpose

Create the cleanest possible speaking experience.

The interface should stay out of the way.

---

## Layout

Large countdown timer.

Microphone status.

Workout prompt pinned at the top.

Waveform visualization.

End Workout button.

---

## Timer

The timer starts automatically when recording begins.

The microphone records continuously.

Users do not need to repeatedly press record.

---

## Display

Remaining time

Current recording duration

Live waveform

Microphone indicator

Workout prompt

---

## Controls

Pause (Future)

Finish Workout

Microphone permission

Nothing else.

---

## Behavior

Recording begins immediately.

The microphone remains active until:

* User presses Finish Workout.
* Timer expires.

If time expires:

Recording automatically stops.

Audio uploads immediately.

---

## Time Recommendations

Beginner

60–90 seconds

Intermediate

2 minutes

Advanced

3–5 minutes

These are recommendations rather than hard limits.

---

## UX Rules

The prompt remains visible but does not scroll.

The waveform should reassure users that recording is active.

The timer should be visually dominant.

No distracting controls.

---

# Upload State

---

## Purpose

Keep users informed while audio is processed.

---

## Layout

Centered.

Minimal.

Progress animation.

---

## Copy

Uploading your workout...

Preparing your coach's feedback...

---

Never expose technical upload progress.

Focus on reassurance rather than percentages.

---

# Error States

Microphone denied.

"We need microphone access to evaluate your communication."

Button

Enable Microphone

---

Recording interrupted.

"Your workout was interrupted."

Options

Continue Recording

Restart Workout

---

Upload failed.

"We couldn't upload your recording."

Retry

Save locally (future)

---

Internet disconnected.

"We'll retry automatically when you're back online."

---

# Accessibility

Keyboard support.

Screen reader labels.

Visible microphone status.

Large timer.

High contrast.

Reduced motion support.

---

# Exit Paths

Finish Workout

↓

Coach Feedback

Leave Workout

↓

Confirmation Dialog

Retry Upload

↓

Coach Feedback

---

# Acceptance Criteria

Users should be able to:

* Understand the prompt immediately.
* Prepare without pressure.
* Record without confusion.
* Complete the workout without needing instructions.
* Trust that their recording has been captured.

The technology should become invisible.

The communication should become the focus.

---

# Steve Jobs Test

Remove every icon.

Remove every animation.

Remove the waveform.

Would someone still understand how to complete the workout?

If not,

simplify further.

Technology should never compete with the conversation.


# FLOW 05

# Workout Completion, Celebration & Coach Feedback

---

# Purpose

This flow transforms effort into emotion.

The user has already done the hard work.

Now the product must make them feel proud enough to return tomorrow.

Feedback should never feel like a report card.

It should feel like a coach helping someone improve.

---

# User Goal

"I want to know how I did."

---

# Business Goal

Increase Day-1 retention.

Increase streak retention.

Increase perceived value.

Encourage sharing.

---

# Emotional Journey

```text
Effort

↓

Relief

↓

Celebration

↓

Recognition

↓

Reflection

↓

Motivation

↓

Return Tomorrow
```

Never interrupt this order.

---

# Screen 1 — Workout Complete

Recording ends.

The screen fades to a calm dark background.

No report appears immediately.

Pause for approximately 500–700 milliseconds.

Let the moment breathe.

---

## Layout

Centered.

Minimal.

No buttons.

No cards.

No distractions.

---

## Copy

🏋️

Workout Complete.

---

Below:

Great job.

You showed up today.

That's how confidence is built.

---

Animation:

The title gently fades upward.

The background subtly brightens.

Nothing flashy.

---

# Screen 2 — XP Celebration

After the completion message,

XP appears.

The number counts upward.

---

Example

```text
+50 XP

Level 6

Progress

██████████░░░░

72%
```

Progress bar fills smoothly.

If a level is earned,

play a separate animation.

Never combine multiple celebrations.

---

# Level Up

When applicable.

Display:

━━━━━━━━━━━━━━

LEVEL UP

Communication Level 7

━━━━━━━━━━━━━━

The card gently expands.

No confetti.

No fireworks.

Achievement should feel premium.

---

# Streak Celebration

Immediately after XP.

Display

🔥

7 Day Streak

Below

Every day matters.

Keep showing up.

---

If a milestone exists

3

7

14

30

50

100

365

Use unique celebration copy.

Example

30 Days

One month of consistency.

You're becoming someone who practices.

---

# Daily Quote

Now display one quote.

Only one.

Examples

━━━━━━━━━━━━━━

Confidence isn't discovered.

It's trained.

━━━━━━━━━━━━━━

Small conversations

create big opportunities.

━━━━━━━━━━━━━━

Tomorrow's confidence

starts with today's repetition.

Never repeat the same quote frequently.

---

# Transition

Only after celebration finishes

does the Coach Feedback appear.

The user has already been rewarded.

Now they're emotionally open to learning.

---

# Screen 3 — Coach Feedback

Purpose

Provide useful,

encouraging,

actionable guidance.

Never overwhelm.

---

Layout

Overall Score

↓

Coach Summary

↓

Strengths

↓

Areas to Improve

↓

Metrics

↓

Transcript (Collapsed)

---

# Overall Score

Large.

Simple.

Avoid unnecessary decimals.

Example

87 / 100

Below

Great Progress.

Keep training.

Never

Excellent

Poor

Bad

The score should encourage improvement.

---

# Coach Summary

Maximum

3–4 sentences.

Example

You explained your ideas clearly and stayed on topic throughout the workout.

Your storytelling felt natural.

Try slowing your pace slightly to make important moments more impactful.

---

# Strengths

Maximum three.

Examples

✓ Clear structure

✓ Easy to follow

✓ Strong examples

Avoid generic praise.

Every point should feel specific.

---

# Improvements

Maximum three.

Example

Speak slightly slower.

Reduce filler words.

Pause before changing ideas.

Every improvement should feel achievable tomorrow.

---

# Metrics

Display only metrics we can confidently measure.

Examples

Clarity

Vocabulary

Structure

Speaking Pace

Filler Words

Duration

Do not invent metrics.

Confidence should only appear if technically supported.

---

# Metric Cards

Simple.

Clean.

Example

```text
Clarity

91

Excellent
```

Never use radar charts in MVP.

---

# Coach Challenge

Always finish with tomorrow.

Example

Tomorrow,

try telling a story using only three key moments.

This creates anticipation.

---

# Transcript

Collapsed by default.

Label

View Transcript

The transcript is secondary.

The experience is primary.

---

# Share Achievement

After feedback.

Display

Share Today's Progress

Generate a beautiful card.

Never share raw scores.

Example

━━━━━━━━━━━━━━

CommunicationGym

Day 18 Complete

🔥 18 Day Streak

+50 XP

━━━━━━━━━━━━━━

The card should promote curiosity.

Not competition.

---

# Primary CTA

Return Home

---

# Secondary CTA

View Transcript

---

# Loading States

Coach is reviewing your workout...

Preparing personalized feedback...

Almost ready...

Rotate messages every few seconds.

Never show an empty spinner.

---

# Error States

Evaluation failed.

We couldn't finish reviewing today's workout.

Retry Evaluation.

Your recording is safe.

Users should never fear losing progress.

---

# Accessibility

Every metric readable.

Screen reader support.

Keyboard navigation.

Reduced motion.

High contrast.

---

# Exit Paths

Return Home

↓

History

↓

Leaderboard

↓

Profile

↓

Close App

---

# Acceptance Criteria

Users should finish this experience feeling:

Rewarded.

Encouraged.

Motivated.

Curious about tomorrow.

Not judged.

Not overwhelmed.

Not exhausted.

---

# Steve Jobs Test

Remove the colors.

Remove the icons.

Remove the animations.

Does the feedback still feel like it came from a thoughtful coach rather than a machine?

If not,

rewrite the experience.

Technology should disappear.

Human encouragement should remain.

---

# Experience Rule

The user should remember one thing after every workout:

"I actually enjoyed practicing."

Not:

"The AI was good."

That emotional distinction is the foundation of CommunicationGym.

# FLOW 06

# History, Leaderboards & Profile

---

# Purpose

These screens exist to reinforce one message:

**You are becoming a better communicator.**

They are not archives.

They are evidence of progress.

Users should leave these screens feeling proud of how far they have come.

---

# User Goal

I want to see my progress.

I want to know where I stand.

I want to stay motivated.

---

# Business Goal

Increase long-term retention.

Encourage streak continuation.

Provide meaningful long-term progression.

Create healthy competition.

---

# Emotional Journey

```text
Reflection

↓

Recognition

↓

Motivation

↓

Commitment

↓

Return Tomorrow
```

---

# FLOW 06A

# Workout History

---

## Purpose

Allow users to revisit previous communication workouts.

History should tell a story.

Not display a spreadsheet.

---

## Layout

Top Navigation

↓

Current Streak Summary

↓

Monthly Calendar

↓

Workout Timeline

↓

Statistics Summary

---

# Calendar

The first thing users see.

Each completed workout fills that day's circle.

Example

```text
M T W T F S S

● ● ● ○ ● ● ○
```

Users should immediately understand:

"I've been consistent."

---

# Workout Timeline

Each workout appears as a card.

Example

```text
Storytelling

Explain a lesson from your childhood.

87/100

+50 XP

July 4

View Report →
```

Cards ordered newest first.

---

# Interaction

Tap card

↓

Full Coach Report

↓

Transcript

↓

Replay Audio (Future)

Nothing else.

---

# Monthly Summary

At the end of each month display

Workouts Completed

Average Score

Total XP

Longest Streak

Favorite Category

This should feel like a fitness summary.

---

# Empty State

No workouts yet.

Instead of an empty page.

Display

```text
Your communication journey begins today.

Complete your first workout.

[ Start Today's Workout ]
```

---

# FLOW 06B

# Global Leaderboard

---

## Purpose

Competition should inspire.

Not discourage.

---

## Philosophy

Users compete with consistency.

Not natural talent.

---

## Layout

Header

↓

Current League

↓

Top 10 Preview

↓

Your Position

↓

Around You

---

# League

Every user belongs to one league.

Examples

Bronze

Silver

Gold

Platinum

Diamond

Master

Legend

Promotion occurs weekly.

Not immediately.

---

# Top Players

Show only top ten.

Display

Rank

Avatar

Name

XP

Current Streak

Nothing else.

---

# Your Position

Example

```text
You

#482

740 XP

Silver League
```

Always visible.

---

# Around You

Instead of showing only Top 10.

Show

Five above.

You.

Five below.

People care more about nearby competition.

---

# Weekly Reset

Every Monday.

XP resets.

Lifetime XP remains.

This allows beginners to compete.

---

# Empty State

Leaderboard unavailable.

Display

Keep training.

The leaderboard will return shortly.

---

# FLOW 06C

# Profile

---

## Purpose

Celebrate identity.

Users should feel ownership of their communication journey.

---

## Layout

Profile Picture

↓

Name

↓

Current Level

↓

Current Streak

↓

Lifetime XP

↓

Achievements

↓

Statistics

↓

Settings

---

# Hero Section

Large avatar.

Communication Level

Current XP

Progress Ring

Current Streak

This section should feel prestigious.

---

# Statistics

Display

Lifetime Workouts

Longest Streak

Average Score

Hours Practiced

Favorite Category

Total Speaking Time

No unnecessary metrics.

---

# Achievements

Examples

First Workout

3 Day Streak

7 Day Streak

30 Day Streak

100 Workouts

Storytelling Master

Consistency Champion

Achievements should unlock naturally.

Never overwhelm users.

---

# Personal Bests

Display

Highest Score

Longest Streak

Most XP in One Week

Longest Workout

Best Improvement Month

This creates long-term goals.

---

# Settings

Minimal.

Theme

Language (Future)

Privacy

Logout

Nothing else.

---

# Notifications (Future)

Placeholder only.

Do not build.

---

# Empty State

Not applicable.

Every authenticated user has a profile.

---

# Accessibility

Every statistic readable.

Large typography.

Keyboard navigation.

Reduced motion support.

---

# Animations

Statistics count upward.

Achievement cards fade in.

Progress ring animates smoothly.

Cards gently elevate on hover.

Transitions under 300ms.

---

# Acceptance Criteria

A user opening Profile should immediately understand:

Who they are becoming.

How much progress they have made.

What they should improve next.

They should feel proud.

Not judged.

---

# Steve Jobs Test

Hide every number.

Hide every icon.

Hide every achievement.

Would this page still communicate identity?

If not,

simplify further.

---

# Future Hooks

Reserved for future versions.

Do not implement in MVP.

* Friends
* Follow Users
* Team Challenges
* Campus Rankings
* Coach Profiles
* Mentor Invitations
* Verified Communication Scores
* Recruiter Profile
* Public Shareable Profile
* Community Feed

These features should fit naturally without redesigning the product architecture.

---

# End of USER_FLOW.md

## Product Experience Summary

The CommunicationGym experience follows one continuous loop.

```text
Landing

↓

Experience Value

↓

Google Login

↓

Onboarding

↓

Training Hub

↓

Daily Spin

↓

Workout Reveal

↓

Thinking Time

↓

Workout Session

↓

Celebration

↓

Coach Feedback

↓

History

↓

Profile

↓

Return Tomorrow
```

Every screen should encourage one action.

Every interaction should reduce friction.

Every workout should strengthen confidence.

Every return should feel rewarding.

CommunicationGym succeeds when users stop opening it because they "have to."

They open it because training has become part of who they are.
