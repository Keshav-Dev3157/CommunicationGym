# COMPONENT_LIBRARY.md

> Version: 0.1
>
> Project Codename: CommunicationGym

---

# Introduction

This document defines every reusable UI component in CommunicationGym.

A component should only exist once.

Every screen should assemble existing components rather than inventing new ones.

Consistency is a product feature.

---

# Component Philosophy

Components are building blocks.

They should be:

* Predictable
* Accessible
* Reusable
* Responsive
* Consistent
* Delightful

Every component should feel like it belongs to the same product.

---

# COMPONENT 01

# Primary Button

---

## Purpose

Represents the most important action on the screen.

Every screen may contain **only one** Primary Button.

---

## Examples

* Spin Today's Workout
* Continue
* Start Workout
* Finish Workout
* Return Home

---

## Size

Height

56px

Width

Auto

Minimum Width

160px

Padding

16px × 24px

---

## States

Default

Hover

Pressed

Loading

Disabled

Focus

Success (Rare)

---

## Behaviour

Hover

Slight elevation

Pressed

Compress by approximately 2%

Loading

Replace label with spinner + text

Disabled

Reduced opacity

No shadow

---

## Accessibility

Minimum touch target

48px

Visible keyboard focus

Screen reader label required

---

## Anti-patterns

Never place two Primary Buttons on one screen.

Never use destructive colors.

Never animate continuously.

---

# COMPONENT 02

# Secondary Button

---

## Purpose

Represents secondary actions.

Examples

View Transcript

Skip

Back

Retry

---

## Style

Outlined

No fill

Subtle hover

Never visually compete with Primary Button.

---

# COMPONENT 03

# Icon Button

---

## Purpose

Compact actions.

Examples

Theme Toggle

Back

Settings

Profile

---

## Size

48px

Square

Centered Icon

---

## Rules

Always include accessible labels.

Never rely only on icon meaning.

---

# COMPONENT 04

# Workout Card

---

## Purpose

The most important card in the application.

Users should immediately understand today's challenge.

---

## Layout

Category

↓

Workout Title

↓

Description

↓

Metadata

↓

Primary CTA

---

## Metadata

Estimated Time

Difficulty

Primary Skill

Current Streak

---

## Behaviour

Card slightly elevates on hover.

Soft shadow.

No excessive gradients.

---

## States

Upcoming

Ready

Completed

Locked (Future)

---

# COMPONENT 05

# Progress Card

---

## Purpose

Shows growth.

Never overwhelms.

---

## Contents

Current Level

XP

Progress Bar

Next Level

---

## Rules

Numbers animate upward.

Progress bar fills smoothly.

Never flash.

---

# COMPONENT 06

# Coach Feedback Card

---

## Purpose

Display coaching insights.

Should feel supportive.

Not analytical.

---

## Structure

Title

↓

Summary

↓

Strengths

↓

Improvements

↓

Metrics

---

## Rules

Maximum

Three strengths.

Maximum

Three improvements.

Avoid paragraphs.

Use concise coaching language.

---

# COMPONENT 07

# Metric Card

---

## Purpose

Display one measurable communication metric.

Examples

Clarity

Vocabulary

Pace

Structure

---

## Layout

Metric Name

↓

Score

↓

Status

---

## Rules

Never compare users.

Only compare previous self.

---

# COMPONENT 08

# XP Progress Bar

---

## Purpose

Visualize progress toward next level.

---

## Behaviour

Animate from previous value.

Never instantly jump.

---

## Labels

Current XP

Remaining XP

Next Level

---

## Rules

Always display numeric progress.

Never rely only on color.

---

# COMPONENT 09

# Achievement Badge

---

## Purpose

Celebrate milestones.

---

## Examples

First Workout

7 Day Streak

100 XP

Level Up

---

## Behaviour

Fade in.

Soft scale.

No bounce.

---

## Variants

Locked

Unlocked

Featured

---

# COMPONENT 10

# Toast Notification

---

## Purpose

Temporary feedback.

Examples

Workout Saved

Progress Updated

Profile Updated

---

## Behaviour

Slide from top.

Disappear automatically.

Maximum

4 seconds.

---

## Rules

Never block interaction.

Never stack more than three.

---

# COMPONENT 11

# Dialog

---

## Purpose

Interrupt only when necessary.

Examples

Leave Workout

Delete Account

Logout

---

## Layout

Title

↓

Description

↓

Actions

---

## Rules

Maximum two buttons.

Primary

Secondary

Never more.

---

# COMPONENT 12

# Bottom Navigation

---

## Purpose

Primary navigation for mobile.

---

## Items

Training

History

Leaderboard

Profile

---

## Rules

Maximum four items.

Always visible.

Current page highlighted.

---

# COMPONENT 13

# Top Navigation

---

## Purpose

Landing page navigation.

---

## Items

Logo

Features

About

Leaderboard

Login

---

## Rules

Minimal.

Never crowded.

---

# COMPONENT 14

# Avatar

---

## Sizes

Small

Medium

Large

Hero

---

## Behaviour

Tap

↓

Open Profile

---

## Rules

Always circular.

Never square.

---

# COMPONENT 15

# Empty State

---

## Purpose

Guide users.

Never leave blank pages.

---

## Structure

Illustration (Optional)

↓

Headline

↓

Description

↓

Primary Action

---

## Example

"No workouts yet."

↓

"Complete today's workout."

↓

Start Workout

---

# Component Rules

Every new component must answer:

Can an existing component solve this?

If yes,

reuse.

Do not create another.

If no,

create it here first,

then implement it.

---

# Design Rule

Components should never feel like separate widgets.

They should feel like one visual language expressed in different forms.

If users notice the components,

the design has failed.

They should notice only the experience.

---

# Steve Jobs Test

Remove every color.

Remove every icon.

Remove every shadow.

Can users still distinguish:

Buttons

Cards

Dialogs

Navigation

Progress

If yes,

the components have clear hierarchy.

If not,

improve structure before decoration.
