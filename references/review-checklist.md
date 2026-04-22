# Project Review Checklist

Use this checklist when reviewing a user's learning project, portfolio project, or interview project.

The goal is not to judge style taste. The goal is to detect whether the project reflects real engineering thinking or just AI-assisted surface assembly.

## Review Outputs

When reviewing, return:

- strongest signals
- weakest signals
- modules the user must personally understand better
- places where AI use is acceptable
- places where AI use has gone too far
- concrete next fixes

Also check whether the review itself follows good coaching discipline:

- is it anchored to the user's current code and attempt
- does it focus on the highest-leverage next issues instead of dumping everything
- does it preserve meaningful work for the user rather than replacing their code reflexively

## 1. Project Positioning

Check:

- Is the target role clear?
- Does the project type match that role?
- Is the scope small enough to finish but large enough to show depth?
- Is there a clear one-line value proposition?

Red flags:

- the project tries to show everything
- there is no clear hiring signal
- the project is mostly visual surface

## 2. Business Realism

Check:

- Is there a believable user flow?
- Is there real state transition complexity?
- Are loading, empty, and error states designed?
- Is there at least one meaningful edge case?

Red flags:

- page collection without flow
- mock business that never creates real data-state pressure
- every page works only in the happy path

## 3. Architecture Quality

Check:

- Are modules split by responsibility rather than appearance?
- Is state ownership clear?
- Are reusable parts truly reusable?
- Is the directory structure likely to scale one step further?

Red flags:

- over-fragmented files with weak boundaries
- everything pushed into global state
- everything left local without a state strategy
- "componentization" used as decoration

## 4. Frontend or Mobile Depth

For frontend, check:

- component abstraction
- state separation
- list and filtering complexity
- performance handling
- environment and testing discipline

For mobile, check:

- weak-network behavior
- lifecycle handling
- loading and retry logic
- device capability integration
- startup and render constraints

Red flags:

- static UI heavy, system behavior light
- no attention to platform-specific risk

## 5. Engineering Quality

Check:

- lint and formatting setup
- type safety discipline
- error handling consistency
- code duplication level
- whether key modules have tests or at least testable structure

Red flags:

- inconsistent style between files suggesting raw AI paste
- dead code and unused abstractions kept after generation
- giant files with mixed responsibilities
- no conventions for naming, error handling, or data flow

## 6. Performance and Stability

Check:

- Did the user identify realistic bottlenecks?
- Are optimizations tied to real risks?
- Is there any caching, debouncing, lazy loading, pagination, or render control where appropriate?
- Are failure states and retries considered?

Red flags:

- "performance optimization" appears only as buzzwords
- expensive UI structures with no mitigation
- poor resilience under slow network or large data

## 7. AI Boundary Quality

Check:

- Which modules were clearly AI-assisted?
- Which modules still show strong user ownership?
- Could the user defend the generated modules in an interview?
- Did AI replace a core learning objective?
- Did AI escalate help too quickly from hinting to full implementation?

Red flags:

- the most important module is obviously AI-written and poorly understood
- code style changes sharply across modules
- complex code exists with no matching reasoning from the user
- abstractions are present but the user cannot justify them
- AI replaced salvageable user code instead of coaching an incremental improvement

## 8. Interview Defensibility

For each major module, ask whether the user can answer:

1. Why this design?
2. What alternatives were considered?
3. What bugs are most likely?
4. How would you debug them?
5. How would this change under a new requirement?

Scoring suggestion:

- `5/5`: strong ownership
- `4/5`: acceptable but needs practice
- `3/5 or below`: this module is not yet interview-safe

Also check whether AI has already helped the user produce a post-completion explanation covering:

- what the module does
- why it is designed this way
- what benefits it brings
- what alternatives exist
- why those alternatives were not chosen here
- how to clearly understand it and describe it to someone else

If this explanation step has not happened, treat the module as incompletely learned even if the code works.

Also check whether the explanation follows a stable structure instead of scattered remarks. A good explanation should cover:

- what it does
- why it exists
- what value it brings
- what the alternatives are
- why those alternatives are not preferred here
- how to form a correct mental model
- how to describe it clearly to another person

## 8.5 Coaching Quality

Check:

- Was the user asked to think before AI proposed the plan?
- Was the exchange kept to one meaningful next step at a time?
- Were debug and review flows structured instead of chaotic?
- Did the AI preserve a real practice loop for the user?

Red flags:

- AI asked for learning but then immediately solved everything
- too many tasks or explanations were pushed in a single step
- feedback restarted from theory instead of using the user's actual attempt

## 9. What Companies Usually Prefer

Use this section to correct the user toward more realistic patterns.

In general, real teams prefer:

- simple and stable architecture over fashionable architecture
- clear state ownership over all-purpose global stores
- reusable modules with actual use cases over speculative abstraction
- targeted performance work over premature optimization
- conventions and maintainability over cleverness

Remind the user:

- enterprise code is often less fancy but more stable
- interviewers care more about tradeoffs than code volume
- GitHub projects worth learning from usually have cleaner boundaries, fewer magical abstractions, and more explicit engineering constraints

## Review Summary Template

Use this structure:

### Strongest Signals

- 3 things that already look like real engineering work

### Weakest Signals

- 3 things that currently look shallow, brittle, or AI-assembled

### Must-Own Modules

- modules the user should rewrite or deeply rehearse personally

### AI-Acceptable Zones

- modules where AI assistance is productive and low-risk

### Next Fixes

- the next 3 highest-leverage changes before the project is shown to others
