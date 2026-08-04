# DESIGN_TOKENS.md

> Version: 0.1
>
> Project Codename: CommunicationGym

---

# Purpose

Design Tokens are the atomic building blocks of CommunicationGym.

They define every reusable visual value across the application.

The purpose of this document is to guarantee consistency.

No component should invent its own spacing, typography, radius, shadows or animation.

If a value is not defined here,

it should not exist.

---

# Design Philosophy

Consistency creates trust.

Users rarely notice perfect consistency.

They immediately notice inconsistency.

Every pixel should feel intentional.

---

# Spacing Scale

CommunicationGym uses an **8-point design system**.

Small exceptions are allowed only where explicitly documented.

| Token    | Value | Usage               |
| -------- | ----: | ------------------- |
| space-0  |   0px | Reset               |
| space-1  |   4px | Tight spacing       |
| space-2  |   8px | Icon spacing        |
| space-3  |  12px | Small gaps          |
| space-4  |  16px | Default spacing     |
| space-5  |  20px | Comfortable spacing |
| space-6  |  24px | Cards               |
| space-7  |  32px | Sections            |
| space-8  |  40px | Large blocks        |
| space-9  |  48px | Hero spacing        |
| space-10 |  64px | Screen sections     |
| space-11 |  80px | Major layout        |
| space-12 |  96px | Landing sections    |

Rule:

Never invent spacing values.

---

# Border Radius

Rounded.

Modern.

Comfortable.

Never sharp.

| Token       | Value |
| ----------- | ----: |
| radius-xs   |   8px |
| radius-sm   |  12px |
| radius-md   |  16px |
| radius-lg   |  20px |
| radius-xl   |  24px |
| radius-pill | 999px |

Usage

Buttons → radius-md

Inputs → radius-md

Cards → radius-lg

Dialogs → radius-xl

Badges → radius-pill

---

# Border Width

| Token         | Value |
| ------------- | ----: |
| border-none   |     0 |
| border-thin   |   1px |
| border-medium |   2px |

Never exceed 2px.

---

# Elevation

Only four elevation levels exist.

| Token       | Usage   |
| ----------- | ------- |
| elevation-0 | Flat    |
| elevation-1 | Buttons |
| elevation-2 | Cards   |
| elevation-3 | Dialogs |

Never stack shadows.

Never create custom elevations.

---

# Shadow Tokens

### Shadow XS

```css
0 1px 2px rgba(0,0,0,.05)
```

Usage

Buttons

Inputs

---

### Shadow SM

```css
0 4px 12px rgba(0,0,0,.08)
```

Usage

Cards

---

### Shadow MD

```css
0 10px 30px rgba(0,0,0,.10)
```

Usage

Dialogs

Workout Card

---

### Shadow LG

```css
0 18px 60px rgba(0,0,0,.14)
```

Rare.

Landing Hero only.

---

# Blur

Avoid excessive blur.

| Token     | Value |
| --------- | ----: |
| blur-none |     0 |
| blur-sm   |   8px |
| blur-md   |  16px |
| blur-lg   |  24px |

Used only for:

Dialogs

Daily Spin overlay

Future Glass elements

---

# Layout Widths

Mobile First.

| Token   |  Width |
| ------- | -----: |
| mobile  |  390px |
| tablet  |  768px |
| desktop | 1280px |
| wide    | 1440px |

Content Width

Maximum

1200px.

Never wider.

---

# Grid System

Desktop

12 Columns

Tablet

8 Columns

Mobile

4 Columns

Every layout follows this grid.

---

# Containers

Small

640px

Medium

960px

Large

1200px

Landing Hero

1280px

---

# Z Index

Never use arbitrary values.

| Layer              | Value |
| ------------------ | ----: |
| Base               |     0 |
| Sticky Header      |   100 |
| Navigation         |   200 |
| Dropdown           |   300 |
| Dialog             |   500 |
| Toast              |   700 |
| Fullscreen Overlay |   900 |
| Emergency Overlay  |  1000 |

---

# Opacity Tokens

| Token       | Value |
| ----------- | ----: |
| opacity-100 |  100% |
| opacity-90  |   90% |
| opacity-80  |   80% |
| opacity-60  |   60% |
| opacity-40  |   40% |
| opacity-20  |   20% |
| opacity-10  |   10% |

Never use arbitrary opacity values.

---

# Icon Sizes

| Token     | Size |
| --------- | ---: |
| icon-xs   | 16px |
| icon-sm   | 20px |
| icon-md   | 24px |
| icon-lg   | 32px |
| icon-xl   | 40px |
| icon-hero | 56px |

Lucide Icons only.

No mixed libraries.

---

# Avatar Sizes

Small

32px

Medium

40px

Large

56px

Profile Hero

96px

---

# Touch Targets

Minimum

48px

Preferred

56px

No interactive element may be smaller.

---

# Dividers

Subtle.

1px.

Low contrast.

Used only to separate meaningfully different content.

Avoid excessive separators.

Whitespace should perform most grouping.

---

# Section Rhythm

Every screen follows:

Large Section

↓

Medium Gap

↓

Component

↓

Small Gap

↓

Related Content

↓

Large Gap

This rhythm should remain consistent throughout the application.

---

# Safe Areas

Respect modern mobile devices.

Support:

iPhone Dynamic Island

Android punch-hole cameras

Bottom gesture navigation

No important content should sit inside unsafe regions.

---

# Token Rules

Never hardcode visual values.

Every reusable value must reference a Design Token.

If a developer feels the need to invent a new spacing, radius or elevation token,

the design system should be updated first.

Consistency is more valuable than creativity.

---

# Steve Jobs Test

Hide every color.

Hide every image.

Hide every icon.

The interface should still feel balanced purely because spacing, rhythm and proportions are correct.

If spacing alone does not create visual harmony,

the layout has failed.
