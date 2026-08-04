# AI_SYSTEM.md

> Version: 0.1
>
> Project Codename: CommunicationGym

---

# Purpose

The AI System is the coaching intelligence behind CommunicationGym.

Its responsibility is not to judge communication.

Its responsibility is to help users become better communicators through consistent, personalized coaching.

Every AI decision should support learning.

Never intimidation.

Never perfection.

---

# Philosophy

CommunicationGym does not build an AI evaluator.

CommunicationGym builds a communication coach.

The distinction matters.

An evaluator measures.

A coach teaches.

Users should always feel that someone is helping them improve,

not grading them.

---

# Product Vision

The AI should become more valuable the longer someone uses CommunicationGym.

Every completed workout should improve future coaching.

The system should gradually understand:

* Strengths
* Weaknesses
* Preferred learning style
* Communication habits
* Improvement trends
* Motivation style

The AI should remember growth,

not conversations.

---

# Coach Identity

The Coach is:

Supportive

Patient

Observant

Specific

Practical

Honest

Encouraging

Professional

The Coach is never:

Harsh

Sarcastic

Judgmental

Overly emotional

Corporate

Verbose

The Coach speaks like an experienced communication trainer.

---

# Core Responsibilities

The Coach Engine is responsible for:

Understanding spoken communication.

Evaluating communication quality.

Generating constructive feedback.

Tracking long-term improvement.

Personalizing future coaching.

Recommending future practice.

Updating Communication DNA.

The Coach is never responsible for making final business decisions.

---

# Coaching Principles

## Principle 1

Celebrate effort before improvement.

Always acknowledge that the user practiced.

---

## Principle 2

Specific beats generic.

Instead of

"You communicated well."

Say

"Your opening clearly introduced the topic before moving into examples."

---

## Principle 3

Teach one improvement at a time.

Avoid overwhelming users.

---

## Principle 4

Feedback should be immediately actionable.

Every suggestion should be something users can try tomorrow.

---

## Principle 5

Always end with encouragement.

The final feeling should be motivation.

---

# AI Pipeline Overview

```text
Workout Completed

↓

Recording Uploaded

↓

Speech Recognition

↓

Speech Metrics

↓

Transcript Cleanup

↓

Prompt Context Builder

↓

Coach Engine

↓

Structured Evaluation

↓

Validation

↓

Database

↓

Communication Profile Update

↓

Coach Feedback Delivered
```

Every stage has a single responsibility.

---

# Pipeline Stage 1

Recording

Purpose

Capture spoken communication.

Output

Audio File.

No analysis occurs here.

---

# Pipeline Stage 2

Speech Recognition

Purpose

Generate transcript.

Requirements

High accuracy.

Timestamp support.

Language detection.

Confidence score.

Output

Transcript.

---

# Pipeline Stage 3

Speech Metrics

Purpose

Extract measurable communication features.

Examples

Speaking duration.

Words per minute.

Pause frequency.

Filler word count.

Silence duration.

Sentence length.

Vocabulary diversity.

These metrics should come from deterministic processing whenever possible.

---

# Pipeline Stage 4

Transcript Cleanup

Purpose

Normalize transcript.

Remove transcription artifacts.

Preserve meaning.

Never rewrite the user's ideas.

The transcript should remain faithful to the original speech.

---

# Pipeline Stage 5

Prompt Context Builder

Purpose

Assemble everything the Coach needs.

Includes:

Transcript

Speech Metrics

Today's Workout

User Goals

Communication Profile

Historical Trends

Prompt Version

This stage prepares structured context for the language model.

---

# Pipeline Stage 6

Coach Engine

Purpose

Interpret communication.

Generate coaching.

Produce structured output.

The Coach should reason about communication,

not simply summarize the transcript.

---

# Pipeline Stage 7

Validation

Purpose

Ensure output follows the required schema.

Reject malformed responses.

Reject missing fields.

Reject unsafe responses.

Never store invalid evaluations.

---

# Pipeline Stage 8

Persistence

Purpose

Store:

Evaluation Report

Skill Scores

Communication Profile Updates

AI Metadata

XP Events

Achievement Events

Everything required for future personalization.

---

# Communication Profile Update

After every evaluation,

update long-term communication knowledge.

Examples

Improving pace.

Vocabulary trend.

Confidence trend.

Storytelling growth.

Preferred challenge difficulty.

This profile powers future recommendations.

---

# Explainability

Every coaching insight should be explainable.

The system should be able to answer:

Why was this suggestion made?

Avoid mysterious scoring.

Transparent coaching builds trust.

---

# Human-Centered Rule

The user should never feel evaluated by software.

They should feel coached by an experienced mentor.

That emotional distinction defines CommunicationGym.

---

# AI Review Checklist

Before every AI release ask:

Does this help the user improve?

Is the advice specific?

Can the user act on it tomorrow?

Is the feedback encouraging?

Would a human coach be proud to give this advice?

If the answer is no,

the model should be improved before release.

---

# Final Principle

The goal of the Coach Engine is not to produce impressive AI responses.

The goal is to help someone become a more confident communicator over months and years.

Every evaluation should contribute to that journey.

The best coaching is the coaching that users quietly apply in real life.


# AI_SYSTEM.md

## Phase 2 — Speech Intelligence & Evaluation Engine

---

# Philosophy

The Coach should never evaluate communication using intuition alone.

Every piece of feedback should be supported by either:

* Measurable speech metrics
* Transcript analysis
* Historical user data
* Communication best practices

The language model generates coaching.

The system generates evidence.

The two should never be confused.

---

# Coach Evaluation Framework

The Coach evaluates communication across multiple dimensions.

Each dimension represents a real communication skill rather than an arbitrary score.

No single metric determines the final evaluation.

---

# Core Communication Dimensions

## 1. Clarity

Question

Can another person easily understand the speaker?

Signals

* Sentence simplicity
* Logical progression
* Minimal ambiguity
* Clear explanations

---

## 2. Structure

Question

Did the speaker organize ideas logically?

Signals

* Beginning
* Middle
* Conclusion
* Smooth transitions

---

## 3. Storytelling

Question

Did the speaker create engagement?

Signals

* Context
* Conflict
* Resolution
* Emotional progression

Not every workout requires storytelling.

Weight this metric only when relevant.

---

## 4. Speaking Pace

Question

Was the pace comfortable?

Signals

* Words per minute
* Pause frequency
* Long silence detection

Never reward speaking fast.

Reward speaking clearly.

---

## 5. Vocabulary

Question

Did the user communicate precisely?

Signals

* Word diversity
* Appropriate vocabulary
* Repetition frequency

Never punish simple language.

Clarity always beats complexity.

---

## 6. Filler Words

Examples

Um

Uh

Like

You know

Basically

Actually

Excessive fillers reduce clarity.

Occasional fillers are normal.

The Coach should never encourage unnatural perfection.

---

## 7. Confidence (Estimated)

Confidence should never be guessed from personality.

Estimate only observable speaking behaviour.

Examples

* Long hesitation
* Frequent restarting
* Incomplete thoughts
* Stable pacing
* Consistent volume (future)

If confidence cannot be measured reliably,

do not score it.

---

## 8. Prompt Relevance

Question

Did the user answer today's workout?

The Coach should avoid rewarding beautifully delivered answers that ignore the prompt.

---

# Skill Weighting

Every workout defines primary and secondary skills.

Example

Storytelling Workout

Storytelling

40%

Structure

20%

Clarity

20%

Vocabulary

10%

Speaking Pace

10%

Interview Workout

Clarity

35%

Structure

30%

Confidence

15%

Vocabulary

10%

Speaking Pace

10%

The evaluation adapts to the workout.

Not every workout uses the same scoring formula.

---

# Evaluation Pipeline

```text id="cg-ai-evaluation"
Recording

↓

Speech-to-Text

↓

Speech Metrics

↓

Workout Context

↓

Communication Profile

↓

Historical Trends

↓

Evaluation Engine

↓

Coach Response

↓

Schema Validation

↓

Database
```

Each stage has a single responsibility.

---

# Prompt Context Builder

Before calling the language model,

assemble structured context.

Never send raw text alone.

Context should include:

User Goals

Communication Rank

Workout Prompt

Workout Category

Transcript

Speech Metrics

Historical Trends

Weakest Skills

Strongest Skills

Current Streak

Prompt Version

Coach Version

Language

This produces far more consistent coaching.

---

# Prompt Architecture

Never write one massive prompt.

Instead divide it into modules.

Module 1

System Identity

↓

Module 2

Evaluation Rules

↓

Module 3

Workout Context

↓

Module 4

Speech Metrics

↓

Module 5

Transcript

↓

Module 6

Historical Context

↓

Module 7

Required JSON Schema

Each module should be versioned independently.

---

# Structured Output

The Coach should never return markdown.

The Coach always returns structured JSON.

Example

```json
{
  "overall_score": 84,
  "summary": "...",
  "strengths": [],
  "improvements": [],
  "next_challenge": "...",
  "skills": {
    "clarity": 90,
    "structure": 82,
    "storytelling": 76
  }
}
```

The frontend controls presentation.

The AI controls meaning.

---

# Evaluation Rules

The Coach must:

Recognize improvement.

Reward effort.

Provide specific examples.

Limit advice.

Recommend tomorrow's focus.

The Coach must never:

Invent facts.

Assume emotions.

Criticize personality.

Judge intelligence.

Comment on appearance.

Diagnose mental state.

Guess demographics.

---

# Feedback Framework

Every evaluation follows the same order.

Celebrate

↓

Observe

↓

Teach

↓

Challenge

↓

Motivate

Never change this order.

It creates emotional consistency.

---

# Coaching Limits

Maximum summary

4 sentences

Maximum strengths

3

Maximum improvements

3

Maximum challenge

1

Maximum motivational sentence

1

Less is better.

---

# Scoring Philosophy

Scores communicate progress.

Not worth.

Users should never feel defined by a number.

The score exists to summarize,

not to judge.

---

# Historical Comparison

Whenever possible,

compare users to themselves.

Instead of

"You speak too quickly."

Say

"Compared to your last five workouts, your pace has become much more consistent."

Progress creates motivation.

Comparison creates confidence.

---

# Hallucination Prevention

Never generate feedback unsupported by evidence.

Every coaching point should be traceable to:

Transcript

Speech Metrics

Historical Trends

Workout Prompt

If evidence does not exist,

omit the suggestion.

Honesty builds trust.

---

# Confidence Score

Each evaluation should include an internal confidence score.

Example

0.96

Very confident.

0.72

Moderately confident.

0.41

Low confidence.

Low-confidence evaluations may trigger a simplified coaching response.

This value remains internal.

---

# Validation Layer

Before saving any evaluation:

Validate schema.

Validate score ranges.

Validate required fields.

Validate JSON.

Reject malformed outputs.

Retry automatically when appropriate.

---

# Prompt Versioning

Every evaluation stores:

Coach Version

Prompt Version

Evaluation Version

Schema Version

Future improvements should never overwrite historical evaluations.

---

# AI Review Checklist

Before deploying a new prompt ask:

Is the advice more specific?

Is it shorter?

Is it more actionable?

Is it more encouraging?

Does it reduce hallucinations?

Can users apply it tomorrow?

If not,

do not release.

---

# Final Principle

The Coach should never try to sound intelligent.

It should try to make the user more intelligent in how they communicate.

That distinction should guide every prompt, every evaluation and every future model upgrade.
# AI_SYSTEM.md

## Phase 3 — Communication DNA & Adaptive Learning Engine

---

# Philosophy

CommunicationGym should never evaluate workouts in isolation.

Every workout is one data point in a much longer journey.

The purpose of AI is not to answer:

"How did you do today?"

The purpose is to answer:

"How are you changing over time?"

This philosophy transforms CommunicationGym from an AI evaluation tool into a lifelong communication coach.

---

# Communication DNA™

## Definition

Communication DNA is the evolving representation of how a person communicates.

It is not a personality test.

It is not a psychological profile.

It is a continuously updated coaching model built from hundreds of real speaking sessions.

Communication DNA should become more accurate after every completed workout.

---

# Guiding Principles

Communication DNA should:

Learn slowly.

Avoid dramatic changes after one workout.

Prioritize long-term patterns over isolated performances.

Never assume traits without evidence.

Update continuously.

Remain explainable.

---

# DNA Components

Every user gradually develops a profile across several dimensions.

## Core Communication Skills

* Clarity
* Structure
* Storytelling
* Persuasion
* Vocabulary
* Speaking Pace
* Listening (Future)
* Leadership Communication
* Interview Communication
* Sales Communication
* Public Speaking

Each skill stores:

Current estimate.

Historical trend.

Confidence of estimate.

Workouts contributing to the estimate.

---

# Behaviour Patterns

The Coach should identify recurring communication behaviours.

Examples:

Frequently rushes endings.

Strong introductions.

Uses relatable examples.

Explains complex ideas clearly.

Relies on filler words under pressure.

Excellent logical sequencing.

These are observations.

Not labels.

---

# Learning Style

The system gradually learns how the user improves.

Examples

Responds well to short feedback.

Improves after practical exercises.

Learns through repetition.

Benefits from storytelling prompts.

Prefers interview simulations.

Never assume.

Only infer after repeated evidence.

---

# Challenge Preference

The Coach records:

Preferred workout length.

Preferred difficulty.

Most completed categories.

Most skipped categories.

Highest performing categories.

Lowest engagement categories.

The objective is personalization,

not optimization for engagement.

---

# Growth Trends

Communication DNA tracks long-term movement.

Examples

Storytelling

Improving steadily.

Vocabulary

Stable.

Confidence

Improving rapidly.

Speaking pace

Plateau.

Growth trends should update gradually.

One workout should never radically change them.

---

# Adaptive Learning Engine

Every workout recommendation should answer:

What should this person practice next?

Not

What random prompt should we show?

Recommendations should balance:

Weaknesses.

Current goals.

Recent practice.

Variety.

Motivation.

Challenge.

Avoid repeating categories unnecessarily.

---

# Curriculum Engine

CommunicationGym should eventually build a personalized curriculum.

Example

Week 1

Speaking Clearly

↓

Week 2

Storytelling

↓

Week 3

Persuasion

↓

Week 4

Handling Objections

↓

Week 5

Presentation Skills

Different users should receive different learning paths.

---

# Recommendation Inputs

The recommendation engine considers:

Communication DNA.

User Goals.

Historical Performance.

Workout Frequency.

Current Streak.

Weak Skills.

Strong Skills.

Workout Diversity.

Difficulty Progression.

Recent Categories.

No recommendation should be purely random.

---

# Long-Term Coaching Memory

The Coach remembers improvement,

not conversations.

Examples

Correct

"The user consistently improves after practicing storytelling."

Incorrect

"On February 18 the user talked about their dog."

Personal content should not become long-term memory unless it directly affects coaching.

---

# Coaching Memory Structure

The Coach maintains:

Persistent strengths.

Persistent weaknesses.

Effective coaching strategies.

Recent improvements.

Long-term plateaus.

Areas needing reinforcement.

This memory evolves slowly.

---

# Plateau Detection

The Coach should recognize when improvement slows.

Example

Vocabulary has remained stable for 25 workouts.

Recommendation

Introduce higher vocabulary challenges.

Offer advanced storytelling exercises.

Plateaus should change future training.

Not simply appear in reports.

---

# Improvement Detection

When genuine improvement occurs,

celebrate it.

Example

Compared to your last ten workouts,

your transitions have become much smoother.

This reinforcement creates confidence.

---

# Confidence of Recommendations

Every recommendation should include an internal confidence value.

High confidence

Evidence across many workouts.

Medium confidence

Emerging pattern.

Low confidence

Insufficient data.

Low-confidence recommendations should remain conservative.

---

# Coaching Personas

The Coach should adapt tone without changing personality.

Examples

Interview Preparation

Focus on clarity and confidence.

Sales Training

Focus on persuasion and objection handling.

Leadership

Focus on influence and structured thinking.

Networking

Focus on conversational flow.

Public Speaking

Focus on storytelling and pacing.

The underlying Coach remains the same.

Only emphasis changes.

---

# Adaptive Difficulty

Difficulty should evolve naturally.

If the user consistently succeeds,

increase challenge.

If the user struggles repeatedly,

reduce complexity.

Users should spend most of their time slightly outside their comfort zone.

---

# Review Cycle

Communication DNA updates after every workout.

Weekly summaries identify trends.

Monthly summaries highlight growth.

Quarterly summaries identify major improvements.

Annual summaries tell the user's communication story.

---

# Explainability

Every adaptive decision should answer:

Why was this workout recommended?

Why did the Coach prioritize this skill?

Why has difficulty increased?

The system should never feel mysterious.

Transparent personalization builds trust.

---

# Human Override

Future coaches or mentors should be able to review Communication DNA.

Human guidance should always take precedence over automated assumptions.

The AI supports coaching.

It does not replace human expertise.

---

# Future Extensions

Communication DNA should eventually support:

Mock Interviews.

Sales Coaching.

Presentation Coaching.

Negotiation Practice.

Leadership Development.

Campus Placement Training.

Founder Pitch Practice.

Language Learning.

Conversation Simulations.

The underlying profile remains unchanged.

Only the coaching context changes.

---

# Success Metrics

The Learning Engine succeeds when:

Users improve over months.

Recommendations feel increasingly relevant.

Workout variety remains high.

Users feel understood.

Feedback becomes more personalized.

Long-term confidence increases.

The Coach becomes more useful with time.

---

# AI Review Checklist

Before modifying the Learning Engine ask:

Does this improve personalization?

Can the recommendation be explained?

Does it encourage learning rather than engagement?

Will this still make sense after 500 workouts?

Does it respect user privacy?

If any answer is no,

redesign the system.

---

# Final Principle

CommunicationGym is not building an AI that talks.

It is building an AI that remembers how people learn.

The greatest strength of the Coach is not intelligence.

It is continuity.

Every workout should help the Coach understand the user a little better.

Every recommendation should make the next workout a little more valuable.

Over months and years, the Coach should evolve from a feedback engine into a trusted communication mentor.

That long-term relationship is the true product.
# AI_SYSTEM.md

## Phase 4 — Coach Engine Architecture & Production Systems

---

# Philosophy

Large Language Models are replaceable.

CommunicationGym's coaching architecture is not.

The platform should be designed so that changing the underlying AI provider requires minimal application changes.

Every layer above the model represents proprietary product intelligence.

---

# Coach Engine Architecture

The Coach Engine consists of independent modules.

```text
Recording

↓

Evidence Engine

↓

Context Builder

↓

Coach Engine

↓

Learning Engine

↓

Communication DNA

↓

Recommendation Engine

↓

Frontend
```

Each module has one responsibility.

No module should perform another module's work.

---

# Evidence Engine

## Purpose

Collect objective facts before any AI reasoning occurs.

The Evidence Engine should never generate opinions.

It should only collect measurable information.

Sources include:

* Transcript
* Speaking duration
* Words per minute
* Pause frequency
* Filler words
* Prompt metadata
* Historical trends
* Workout category
* Previous coaching

The output becomes structured evidence.

---

# Context Builder

## Purpose

Transform evidence into a complete coaching context.

Inputs

* Evidence
* Communication DNA
* User Goals
* Current Workout
* Historical Progress
* Coach Version
* Prompt Version

Output

One structured context object.

No business logic exists inside prompts.

Prompts receive complete context.

---

# Coach Engine

## Purpose

Interpret evidence.

Never invent evidence.

Responsibilities

* Explain observations
* Teach improvements
* Encourage progress
* Generate structured coaching

The Coach never:

Guesses personality.

Diagnoses mental state.

Infers demographics.

Makes unsupported claims.

---

# Learning Engine

## Purpose

Update long-term understanding.

After every completed workout:

Update Communication DNA.

Detect improvements.

Detect plateaus.

Adjust recommendations.

Increase confidence where evidence accumulates.

The Learning Engine never changes historical evaluations.

It only updates future coaching.

---

# Recommendation Engine

## Purpose

Choose the next best workout.

Recommendations balance:

* Weak skills
* User goals
* Variety
* Motivation
* Difficulty progression
* Recent categories
* Long-term curriculum

Randomness should only break ties.

---

# Communication DNA Update Rules

The profile should evolve slowly.

One workout should not dramatically change identity.

Suggested weighting:

Recent 10 workouts

40%

Previous 40 workouts

40%

Older history

20%

This prevents noisy recommendations.

---

# Prompt Independence

Prompts should never contain:

Business rules.

XP logic.

Level calculations.

Achievement logic.

Recommendation algorithms.

Those belong in application code.

Prompts receive context.

They do not implement product logic.

---

# Structured Contracts

Every stage communicates using typed JSON.

Never parse natural language between services.

Example stages:

Evidence Object

↓

Coach Request

↓

Coach Response

↓

Evaluation Report

↓

Database Record

Strict schemas reduce failures.

---

# AI Provider Abstraction

The application should not depend on a single provider.

Supported architecture:

```text
Coach Engine

↓

AI Adapter

↓

OpenAI

Anthropic

Gemini

Future Local Models
```

Changing providers should not require frontend changes.

---

# Reliability Strategy

If evaluation fails:

Retry automatically.

If retry fails:

Move to retry queue.

If retry queue fails:

Notify operations.

Never lose user recordings.

Never silently discard evaluations.

---

# Timeout Strategy

Speech Recognition

Independent timeout.

LLM Evaluation

Independent timeout.

Profile Update

Independent timeout.

Leaderboard Update

Independent timeout.

Failures should be isolated.

---

# Cost Strategy

Use expensive models only where necessary.

Potential routing:

Speech Recognition

Specialized speech model.

Coaching

High-quality reasoning model.

Summaries

Lower-cost model.

Background analysis

Budget model.

Always optimize for coaching quality per dollar.

---

# Quality Assurance

Every new Coach version should be evaluated against benchmark workouts.

Metrics include:

* Coaching quality
* Hallucination rate
* Schema compliance
* User satisfaction
* Cost per evaluation
* Average latency

New versions should outperform previous ones before release.

---

# Human Review Framework

Future capability.

Selected evaluations may be reviewed by human communication experts.

Human reviews improve:

Prompt design.

Scoring.

Recommendation quality.

The AI learns from product improvements—not from private user conversations.

---

# Privacy by Design

The Coach should remember learning patterns.

Not personal stories.

Example

Store:

"User improves with storytelling exercises."

Do not store:

"The user spoke about their family vacation."

Training data should remain focused on communication.

---

# Observability

Track internal system health.

Examples

Transcription success rate.

Evaluation success rate.

Average processing time.

Schema validation failures.

Retry counts.

Provider outages.

These metrics are operational.

They are not user-facing.

---

# Failure Philosophy

When uncertainty is high,

the Coach should say less.

Never invent feedback to fill empty space.

Honest coaching builds long-term trust.

---

# AI Principles

1. Evidence before opinion.
2. Coach before evaluator.
3. Personalization before optimization.
4. Long-term growth before short-term engagement.
5. Transparency before complexity.
6. Reliability before novelty.

Every future AI feature should follow these principles.

---

# Final Architecture

```text
User

↓

Workout

↓

Recording

↓

Evidence Engine

↓

Context Builder

↓

Coach Engine

↓

Learning Engine

↓

Communication DNA

↓

Recommendation Engine

↓

Evaluation Report

↓

Database

↓

Training Hub

↓

Tomorrow's Workout
```

This is the complete coaching loop.

Every completed workout makes tomorrow's workout more valuable.

That compounding effect—not the language model—is CommunicationGym's long-term advantage.

---

# Final Principle

CommunicationGym is not an AI application.

It is a communication training platform powered by AI.

If a better language model becomes available tomorrow, we should be able to adopt it without changing our product philosophy, coaching framework, or learning system.

The technology may evolve.

The coaching principles should remain stable.
