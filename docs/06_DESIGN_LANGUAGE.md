# DESIGN_LANGUAGE.md

> Version 0.1
>
> Project Codename: CommunicationGym

---

# Introduction

CommunicationGym is not another AI SaaS.

It is a consumer product.

People should enjoy opening it.

The interface should disappear behind the experience.

Users should remember how the product made them feel,

not what components it used.

Every future screen, animation, interaction and component should follow this document.

If implementation conflicts with this document,

this document wins.

---

# Design Philosophy

CommunicationGym should feel like stepping into a premium training studio.

Not a classroom.

Not a dashboard.

Not a productivity app.

Not a corporate LMS.

The experience should communicate:

"I'm about to improve."

before the user even starts today's workout.

---

# Emotional Principles

Every screen should create one dominant emotion.

Landing

Curiosity

↓

Onboarding

Commitment

↓

Training Hub

Motivation

↓

Workout

Focus

↓

Coach Feedback

Growth

↓

Profile

Pride

Never mix multiple emotions on one screen.

Every page should have one emotional purpose.

---

# Personality

CommunicationGym is

Calm

Premium

Athletic

Friendly

Focused

Modern

Human

Optimistic

Supportive

Never

Loud

Flashy

Corporate

Cold

Robotic

Childish

Aggressive

---

# Visual Philosophy

Imagine the product was designed by

Apple

↓

Linear

↓

Nike

↓

Notion

↓

Arc Browser

Every influence should be visible.

None should dominate.

---

# Design Principles

## Principle 1

Remove before adding.

If removing an element does not reduce usability,

remove it.

---

## Principle 2

Whitespace is a feature.

Empty space increases confidence.

Never try to fill every pixel.

---

## Principle 3

One screen.

One purpose.

Every screen should have exactly one primary action.

Everything else supports it.

---

## Principle 4

Motion teaches.

Animation exists to explain.

Not entertain.

---

## Principle 5

Delight should be subtle.

The product should smile.

Never shout.

---

# Visual Hierarchy

Every screen follows

```text
Primary Action

↓

Primary Information

↓

Supporting Information

↓

Navigation

↓

Decoration
```

Decoration should always have the lowest priority.

---

# Typography Philosophy

Typography is the interface.

Avoid decorative fonts.

Use typography to create hierarchy instead of color.

Users should understand importance before reading.

---

# Font Recommendation

Primary

Geist

Fallback

Inter

System

These work exceptionally well with Next.js and Lovable.

---

# Font Weights

Display

700

Heading

600

Body

400

Caption

400

Buttons

600

Never use more than four font weights.

---

# Reading Width

Maximum

70 characters per line.

Reading should never feel tiring.

---

# Color Philosophy

The interface should work beautifully in both Light and Dark Mode.

Dark Mode is not an afterthought.

Both themes receive equal design attention.

---

# Theme

Follow System Theme by default.

Allow manual override.

Remember user preference.

---

# Color Emotion

Background

Quiet

Surface

Comfortable

Primary

Confident

Success

Encouraging

Warning

Gentle

Error

Helpful

Never alarming.

---

# Accent Color

Accent color represents progress.

Not branding.

Use it sparingly.

Accent should attract attention only to:

Primary CTA

Progress

Selected State

Active Navigation

Everything else remains neutral.

---

# Contrast

Readable before beautiful.

Never sacrifice readability for aesthetics.

AA accessibility minimum.

AAA whenever practical.

---

# Border Radius

Default Radius

16px

Large Cards

20px

Small Buttons

14px

Inputs

16px

Dialogs

24px

Everything should feel soft,

not bubbly.

---

# Shadows

Use shadows to communicate elevation.

Not decoration.

Three levels only.

Small

Medium

Large

Never stack shadows.

---

# Borders

Prefer borders over shadows whenever possible.

Borders should be subtle.

Never heavy.

---

# Icons

Icon Library

Lucide

Rounded style.

Consistent stroke width.

Never mix icon libraries.

---

# Icon Rules

Every icon must communicate meaning.

Never decorate with icons.

Icons should never replace text.

---

# Illustration Philosophy

Illustrations are optional.

The interface should work perfectly without them.

Illustrations exist only to reinforce emotion.

Never explain functionality.

---

# Cards

Cards should feel like paper.

Not floating glass.

Comfortable.

Readable.

Touchable.

Never overcrowded.

---

# Buttons

Buttons communicate confidence.

Not urgency.

Primary Buttons

Filled.

Secondary

Outlined.

Ghost Buttons

Text only.

Never more than one Primary Button per screen.

---

# Input Fields

Minimal.

Rounded.

Large touch targets.

Clear focus state.

No unnecessary borders.

Placeholder text should never replace labels.

---

# Forms

One question per screen whenever possible.

Reduce cognitive load.

Avoid long forms entirely.

---

# Empty States

Never leave users with blank pages.

Every empty state should answer:

Why is this empty?

What should I do next?

---

# Loading States

Never display

Loading...

Instead

Preparing today's workout...

Reviewing your communication...

Almost ready...

Loading should feel purposeful.

---

# Error States

Never blame the user.

Instead of

You did something wrong.

Say

Something went wrong.

Let's try again.

The tone remains calm.

---

# Motion Philosophy

Motion should feel physical.

Never cartoon-like.

Never exaggerated.

Every movement should have intention.

---

# Animation Timing

Hover

150ms

Tap

120ms

Card

200ms

Modal

250ms

Page

300ms

Wheel

1500ms

Celebrate

600ms

No animation exceeds

1500ms.

---

# Animation Curves

Use smooth easing.

Avoid bounce.

Avoid elastic.

Avoid gimmicks.

Movement should feel premium.

---

# Hover Behaviour

Cards

Slight lift.

Buttons

Slight darken.

Navigation

Soft underline.

Nothing dramatic.

---

# Success Moments

Success deserves attention.

Not fireworks.

Examples

Workout Complete

Level Up

Achievement

Streak

XP

Every celebration should feel earned.

---

# Sound Philosophy (Future)

Sound should reward.

Never interrupt.

Every sound should be soft.

Organic.

Minimal.

Mute by default on web.

---

# Mobile First

Design every screen for mobile first.

Desktop expands.

Mobile defines the experience.

---

# Responsive Philosophy

Layouts should adapt naturally.

Never create separate experiences.

One product.

Multiple screen sizes.

---

# Accessibility

Support keyboard navigation.

Reduced motion.

High contrast.

Large touch targets.

Readable typography.

Screen readers.

Accessibility is a feature.

Not a checklist.

---

# Three Second Rule

Every screen should answer:

Where am I?

↓

What should I do?

↓

What happens next?

Within three seconds.

If not,

the screen is too complicated.

---

# Zero Decoration Rule

Nothing exists only because it looks cool.

Every pixel earns its place.

Every animation earns its duration.

Every color earns attention.

---

# Steve Jobs Test

Hide every color.

Hide every shadow.

Hide every icon.

Hide every animation.

Can a first-time user still understand exactly what to do?

If yes,

the design succeeds.

If not,

simplify.

Always choose clarity over cleverness.

---

# Final Principle

CommunicationGym should never feel like software.

It should feel like a place people enjoy returning to every day.

When users close the app,

they shouldn't remember the interface.

They should remember how confident they felt after using it.
