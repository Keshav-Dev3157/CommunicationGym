# MOTION_SYSTEM.md

> Version: 0.1
>
> Project Codename: CommunicationGym

---

# Purpose

Motion is not decoration.

Motion explains.

Motion reassures.

Motion rewards.

CommunicationGym should feel alive without feeling busy.

Users should rarely notice animations.

They should simply feel that every interaction behaves naturally.

---

# Motion Philosophy

Every movement must answer one question.

> Why is this moving?

If no meaningful answer exists,

the animation should not exist.

---

# Emotional Goals

Motion should create

Confidence

↓

Curiosity

↓

Focus

↓

Achievement

↓

Calm

Never

Chaos

Distraction

Confusion

Urgency

---

# Design Rule

Motion should imitate physics.

Not cartoons.

Not games.

Objects should feel like they have:

Weight

Momentum

Purpose

Nothing should bounce unnecessarily.

Nothing should wiggle.

Nothing should spin endlessly.

---

# Motion Principles

## Principle 01

Immediate Response

Every tap receives feedback within

100 milliseconds.

The interface should never feel unresponsive.

---

## Principle 02

One Animation

One Purpose

Every animation teaches something.

Examples

Button

↓

Pressed

Card

↓

Selected

Workout

↓

Completed

Progress

↓

Increased

Never animate multiple unrelated properties simultaneously.

---

## Principle 03

Reward

After

Action

Never before.

Users act.

Then the interface celebrates.

Never celebrate anticipation.

Celebrate achievement.

---

## Principle 04

Focus

Motion should guide the eye.

Not steal attention.

If users watch the animation instead of the content,

the animation is too strong.

---

# Motion Timing Scale

Instant

100ms

Fast

150ms

Normal

200ms

Comfortable

250ms

Page Transition

300ms

Celebration

600ms

Daily Spin

1500ms

No animation should exceed

1500 milliseconds.

---

# Easing

Default

Ease Out

Page

Ease In Out

Wheel

Custom smooth deceleration

Dialogs

Ease Out

Hover

Linear

Never use bounce.

Never use elastic.

Never overshoot.

---

# Interaction Feedback

Every interactive element should acknowledge input.

Immediately.

---

# Buttons

Hover

Slight elevation

Pressed

Scale to

98%

Release

Return smoothly

Loading

Replace label

Do not resize button

---

# Cards

Hover

Lift

2–4px

Shadow slightly increases

Pressed

Return to original elevation

Selected

Soft accent border

Never flash.

Never pulse continuously.

---

# Navigation

Active item

Smooth highlight transition

Inactive items

Remain visually stable

No jumping.

---

# Form Inputs

Focus

Border color transitions

Placeholder fades

Cursor appears immediately

Errors animate gently

Never shake inputs.

---

# Progress Bars

Always animate forward.

Never jump instantly.

Never animate backwards unless intentionally resetting.

Duration

500ms

---

# Numbers

XP

Level

Score

Counters should animate upward.

Never instantly change.

Animation Duration

400–600ms

---

# Lists

Items appear

Top to bottom

20–30ms stagger

Maximum

Eight visible animations

Never animate huge lists.

---

# Dialogs

Open

Fade

Scale

98%

↓

100%

Close

Fade

↓

Scale

98%

Maximum

250ms

---

# Toasts

Slide from top

Fade in

Pause

Fade out

Never interrupt interaction.

---

# Hover Philosophy

Desktop only.

Hover exists to confirm.

Not entertain.

Maximum movement

2px

---

# Loading Philosophy

Loading is communication.

Not waiting.

Instead of

Loading...

Use

Preparing today's workout...

Reviewing your communication...

Almost ready...

Movement should imply progress.

Never uncertainty.

---

# Skeletons

Skeletons should shimmer slowly.

Never pulse.

Never flash.

Maximum duration

Until content loads.

---

# Empty States

Appear instantly.

No unnecessary animation.

Primary CTA fades upward.

---

# Error States

Appear calmly.

Avoid alarming motion.

No shaking.

No flashing.

No aggressive red transitions.

The product should always feel in control.

---

# Accessibility

Respect reduced motion settings.

If the user prefers reduced motion

Replace

Movement

With

Opacity changes.

All interactions remain understandable.

---

# Performance Rules

Prefer CSS transforms.

Avoid layout shifts.

Avoid expensive animations.

Maintain

60 FPS

Wherever possible.

---

# Motion Hierarchy

Primary Action

↓

Primary Feedback

↓

Supporting Animation

↓

Decoration

Decoration should always be the first thing removed.

---

# Steve Jobs Test

Disable every animation.

Does the interface still make sense?

If yes,

the motion is supporting the experience.

If no,

the interface depends too heavily on animation.

Redesign the interaction.

---

# Final Principle

Users should never think:

"That animation was cool."

They should think:

"That app feels incredibly smooth."

The difference is what makes software feel premium.




# MOTION_SYSTEM.md

## Phase 2 — Signature Motion & Experience Choreography

---

# Philosophy

CommunicationGym should have a recognizable rhythm.

Users should subconsciously know where they are in the experience based purely on movement.

Motion becomes part of the product's identity.

If someone records the interface without the logo,

the movement should still feel like CommunicationGym.

---

# Signature Motion 01

# Landing Hero

---

## Purpose

Create curiosity.

Not excitement.

The landing page should feel alive before interaction.

---

## Motion

Navigation

↓

Fade Down

200ms

---

Headline

↓

Fade Up

250ms

---

Description

↓

Fade Up

280ms

---

Primary CTA

↓

Fade Up

320ms

---

Daily Wheel

↓

Scale

98%

↓

100%

↓

Soft breathing animation begins

---

## Wheel Idle Animation

The wheel should never remain completely static.

Instead

Every 8–10 seconds

Scale

100%

↓

101%

↓

100%

Very subtle.

Almost unnoticeable.

Purpose

Signal interactivity.

Never demand attention.

---

# Signature Motion 02

# Spin Today's Workout

This is CommunicationGym's signature interaction.

It should feel engineered.

Not random.

---

## Sequence

User taps

Spin Today's Workout

↓

Button compresses

↓

Button expands back

↓

Background gently blurs

↓

Wheel enlarges

↓

Category labels sharpen

↓

Wheel accelerates

↓

Constant speed

↓

Smooth deceleration

↓

Small pause

↓

Selected category glows

↓

Workout card fades upward

↓

Wheel shrinks slightly

↓

Focus moves to workout

---

## Timing

Button

120ms

Blur

180ms

Wheel expansion

220ms

Acceleration

350ms

Rotation

750ms

Deceleration

400ms

Reveal

300ms

Total

≈1.5 seconds

---

## Design Rule

The wheel never feels like gambling.

The destination is already chosen.

The wheel reveals it.

---

# Signature Motion 03

# Workout Reveal

Purpose

Transition from excitement

↓

Preparation

---

The workout card

Slides upward

while fading in.

Metadata appears in sequence.

Category

↓

Prompt

↓

Duration

↓

Skill

↓

CTA

Each separated by

40ms

The user reads naturally.

---

# Signature Motion 04

# Thinking Time

Everything slows.

The interface should feel quieter.

---

Prompt remains fixed.

Timer gently scales every second.

No ticking animation.

No bouncing.

No countdown stress.

The timer should encourage thinking.

Not urgency.

---

# Signature Motion 05

# Workout Session

Recording begins.

---

Microphone

Small pulse every second.

Not continuous.

Waveform

Responds to voice.

Never loops.

Silence

↓

Flat waveform.

Speaking

↓

Real waveform.

---

Timer

Shrinks smoothly every second.

Never jumps.

---

When 15 seconds remain

Timer gently changes emphasis.

No flashing.

No red.

---

When recording ends

Waveform slowly settles.

Timer freezes.

Background subtly darkens.

Transition begins.

---

# Signature Motion 06

# Upload

Purpose

Reduce anxiety.

---

Sequence

Workout ends

↓

Waveform disappears

↓

Uploading

↓

Coach is reviewing...

↓

Preparing insights...

↓

Almost ready...

Messages dissolve smoothly.

Never rotate abruptly.

---

# Signature Motion 07

# Workout Complete

This becomes our emotional signature.

---

Sequence

Background darkens.

500ms pause.

Workout Complete

fades upward.

↓

300ms

↓

XP appears.

Counts upward.

↓

Progress bar fills.

↓

If Level Up

Pause.

↓

Level card expands.

↓

Level text appears.

↓

Pause.

↓

Streak appears.

↓

Pause.

↓

Daily quote fades upward.

↓

Coach Feedback begins.

Never rush.

Every reward gets its own moment.

---

# Timing

Workout Complete

500ms

XP

600ms

Level

600ms

Streak

500ms

Quote

400ms

Coach

300ms

Total

≈3 seconds

---

# Signature Motion 08

# Coach Feedback

Purpose

Avoid overwhelming users.

---

Do NOT reveal everything simultaneously.

Instead

Overall Score

↓

Summary

↓

Strengths

↓

Improvements

↓

Metrics

↓

Transcript

Each section fades upward.

80ms apart.

The user naturally scrolls.

---

# Metric Cards

Cards animate only when entering viewport.

Score counts upward.

Progress ring fills.

No flashing.

---

# Transcript

Collapsed.

Expands downward.

Never pushes content suddenly.

Animate height.

---

# Signature Motion 09

# XP & Level

XP

Counts upward.

Every increment feels earned.

Level

Appears only after XP completes.

Progress bar

Never resets instantly.

It empties.

↓

Pauses.

↓

Refills.

↓

Level appears.

This sequence communicates achievement.

---

# Signature Motion 10

# Navigation

Changing tabs

Does not feel like page reload.

Instead

Current page

↓

Fade

95%

↓

Slide

8px

↓

Next page

Slides upward.

No dramatic transitions.

---

# Signature Motion 11

# Theme Change

Switching

Dark

↓

Light

or

Light

↓

Dark

Should feel continuous.

Duration

250ms

No flash.

No white screen.

---

# Signature Motion 12

# Pull To Refresh (Future Mobile)

Drag

↓

Progress ring appears.

↓

Release

↓

Ring completes.

↓

Content refreshes.

Never show a spinner.

---

# Celebration Hierarchy

Only these deserve celebration.

Workout Complete

XP

Level Up

Achievements

Milestone Streaks

Nothing else.

Do not celebrate every click.

Celebrate meaningful effort.

---

# Motion Budget

One screen should never contain more than:

One major animation.

Three supporting animations.

Unlimited subtle state changes.

If everything moves,

nothing feels important.

---

# Motion Consistency Rules

Movement should always follow

Top

↓

Bottom

Left

↓

Right

Small

↓

Large

Never reverse these patterns without purpose.

Users subconsciously learn them.

---

# Performance Rules

Target

60 FPS

No layout thrashing.

GPU accelerated transforms.

Avoid animating:

Width

Height

Top

Left

Whenever possible.

Prefer:

Opacity

Transform

Scale

Translate

---

# Reduced Motion

When users enable reduced motion.

Replace:

Movement

With

Opacity

Timing

Hierarchy

Never remove feedback entirely.

Accessibility must preserve understanding.

---

# Motion Review Checklist

Before shipping any animation ask:

Does it explain?

Does it reward?

Does it guide attention?

Can it be shorter?

Would removing it make the experience worse?

If the answer is no,

remove it.

---

# Signature Identity

If someone used CommunicationGym for one week,

closed the app,

and opened it six months later,

they should immediately recognize it.

Not because of the logo.

Not because of the colors.

Because of how it moves.

That is the purpose of this Motion System.

---

# Final Principle

Movement is part of the coaching experience.

CommunicationGym should never feel like software reacting.

It should feel like a thoughtful coach responding.

Every transition,

every reveal,

every celebration,

every pause,

should quietly reinforce one idea:

**You're getting better every day.**
