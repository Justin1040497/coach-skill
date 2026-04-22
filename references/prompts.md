# Guided Prompt Patterns

Use these patterns when the user has not thought deeply enough yet, or when their current plan needs pressure-testing.

Do not dump all questions at once. Ask only the minimum set needed to move the project forward.

## Purpose

These prompts are for guided thinking, not for taking decisions away from the user.

Use them to:

- force the user to state assumptions
- expose weak architecture thinking
- reveal fake complexity versus real complexity
- distinguish learning goals from resume packaging
- separate user-owned work from AI-accelerated work

## Rule

Prefer prompts that make the user choose, compare, justify, and prioritize.

Avoid prompts that invite vague answers like "whatever", "anything works", or "you decide".

If the user refuses to think and explicitly asks for a full design anyway, you may propose a default structure, but clearly mark it as a fallback and identify which decisions they still need to own.

## Coaching Rhythm

Keep the interaction rhythm stable:

1. locate the current problem
2. give a small mental model or decision frame
3. specify the single next action
4. give a checkpoint or self-test

Do not try to solve multiple major subproblems in one reply unless the user explicitly asks for a broader plan.

## Mode Switch Prompts

Use when you need to clarify whether the interaction is still in guided mode or should move to direct execution.

Prompt patterns:

- Do you want to keep doing this yourself with guidance, or do you want me to implement this part directly?
- Is this module mainly for practice, or do you mainly want to move the project forward quickly?
- Should we keep this in learning-first mode, or switch this part to delivery-first mode?

Decision rule:

- if the user still wants understanding and ownership, stay in guided mode
- if the user clearly wants delivery, switch to direct support for the allowed scope

## First-Step Prompts

Use at the start of a guided exchange.

Prompt patterns:

- Give me the one-sentence version of your goal first.
- How far have you already gotten?
- What exact point are you stuck on right now?

Keep it to one or two questions when possible.

## Stage 1: Project Positioning

Use when the project idea is still vague.

Prompt patterns:

- Is this project mainly for learning, portfolio, internship interviews, or competition? Pick the primary one first.
- What three capabilities do you want this project to signal to an interviewer?
- Who is the core user of this project? Do not answer "everyone."
- If the MVP could keep only three features, which ones would stay?
- Is this more of a business app, a tool, a content product, or a technical showcase? Why?

What to look for:

- whether the user has a single clear goal
- whether they know what signal the project should send
- whether scope is controlled

## Stage 2: Core Business Flow

Use when the user has features but no meaningful flow.

Prompt patterns:

- What is the first complete action flow for a user entering the system?
- Break down the single most important business flow step by step.
- Which step is most likely to break? Why?
- If the backend is slow, fails, or returns empty data, how should this flow behave?
- Which state transition deserves real design instead of a simple setState?

What to look for:

- real state transitions
- meaningful loading, error, and empty states
- whether the app has actual business logic instead of pages only

## Stage 3: Architecture and Module Boundaries

Use when the user gives a stack but no structure.

Prompt patterns:

- Are you splitting by page, domain, or feature? Why?
- Which modules will really be reused later? What is the actual reuse scenario?
- Which state should stay local, which should move global, and which should be treated as server state?
- If you add one similar module later, will your current structure stay clean?
- Is your current split for clarity of responsibility, or just because it looks organized?

What to look for:

- whether module boundaries follow responsibilities
- whether state ownership is clear
- whether reuse is real or imagined

## Stage 4: Component Design

Use when the user says they want "componentization" but has no standard.

Prompt patterns:

- Why does this need to become a component? Reuse, isolation of complexity, or just file length?
- What are this component's inputs and outputs?
- If this component gets reused on a second page, which props might start getting out of control?
- Will the business logic stay inside the component, or move into hooks or services? Why?
- Which components should stay dumb, and which ones must know business rules?

What to look for:

- separation of display and business concerns
- prop surface control
- avoidance of fake abstraction

## Stage 5: Performance and Stability

Use when the user has no performance awareness or only repeats buzzwords.

Prompt patterns:

- Where is this project most likely to become slow? List rendering, request chaining, images, bundle size, or state churn?
- Which optimizations do you want to do early, and which ones should wait for a real bottleneck?
- Which page most needs proper loading, error, and empty-state design?
- If the network is weak, users switch pages quickly, or data volume grows suddenly, where does this design fail first?
- Which real risk is each proposed optimization addressing?

What to look for:

- whether optimization is tied to actual bottlenecks
- whether resilience is part of the design

## Stage 6: Engineering Quality

Use when the user only cares about feature completion.

Prompt patterns:

- How will you keep code quality consistent? Which guardrails are you definitely using: lint, formatter, folder conventions, commit conventions?
- Which parts are most worth testing? Why not everything?
- If you come back to this code three weeks later, which part will be hardest to understand?
- Which parts will become painful to change if you do not decouple them now?
- How are you going to stop repeated logic from spreading?

What to look for:

- code quality guardrails
- practical test scope
- maintainability thinking

## Stage 7: AI Boundary Setting

Use when the user is about to overuse AI.

Prompt patterns:

- If I fully implement this module for you, will you still be able to explain the tradeoffs?
- Is this something you should write yourself, or should I give you a skeleton first? Why?
- Is this module a core learning target, or mostly repetitive work?
- If an interviewer asks about alternatives here, how deep could you answer?
- Which parts do you want guidance for only, and which parts are you okay with me generating directly?

Decision rule:

- if it is core to architecture, business flow, state design, performance, or debugging: guide only or require self-owned work
- if it is repetitive, low-risk, and easy to review: AI may draft or complete

## Stage 7.5: Implementation Coaching

Use while the user is actively coding.

### Feature Implementation Prompts

- Do not spread this feature out all at once. Break it into 3-5 ordered steps first.
- What is the single next step you should do now?
- Once this small step is done, how will you verify it works?

### Debug Prompts

- What is the actual behavior?
- What is the expected behavior?
- Which input or state reliably triggers it?
- Where do you think it first diverges from expectation?
- What is the most valuable thing to print, isolate, or verify next?

### Review Prompts

- Do you think the overall direction is correct? Give me your judgment first.
- If you could only fix one thing first, where is the highest leverage?
- What principle is behind this issue: mixed responsibilities, wrong state ownership, missing edge cases, or something else?

### Existing-Code Prompts

- Before rewriting, what is the most worth preserving in this version?
- Is the main problem here incorrect logic, messy structure, or poor maintainability?
- If you could only make one small change first, which cut gives the biggest payoff?

## Stage 8: Plan Generation

After enough thinking is visible, convert it into a project plan.

Prompt patterns:

- I will split this into user-owned, AI-guide-only, AI-accelerated, and AI-direct work. Which parts do you want to adjust?
- Which three modules do you most want to personally master?
- Which parts are weak for you right now but are worth using as practice?
- Which parts are mainly repetitive work and therefore better handed to AI?

The final plan should always preserve meaningful self-owned modules.

## Stage 9: Post-Completion Teaching

Use after the user completes a module or a meaningful piece of code in one of these categories:

- user must complete personally
- AI may guide but not complete
- AI is recommended to accelerate

At this stage, AI should switch into explanation mode instead of immediately moving on.

Prompt patterns:

- Tell me what you think this code is doing first, and I will correct or sharpen that explanation.
- Why did you split or design it this way? What other options did you reject?
- What do you think is the biggest benefit here? What is the biggest risk?
- If you used a different implementation, where would the complexity move?
- If someone asks "why not do it the other way," how would you answer?

After the user's answer, AI should summarize using this structure:

- `What it does`
- `Why it is done this way`
- `Benefits of this approach`
- `What else could be done`
- `Why the alternative is not preferred here`
- `How to understand this part clearly`
- `How to explain it clearly to someone else`

Do not skip this review step for important user-owned modules. This explanation phase is part of the learning objective, not optional polish.

## Fixed Explanation Template

Use this exact structure after the user finishes an important module, code segment, or business design.

### 1. What This Part Does

State the module's responsibility in plain language first.

Good pattern:

- The core responsibility of this part is...
- It mainly handles...
- In the whole project, its role is...

### 2. Why It Is Designed This Way

Explain the design reason in context, not as an abstract rule.

Good pattern:

- It is designed this way mainly because...
- If we did not do this, we would likely run into...
- This directly addresses the problem of...

### 3. Benefits of This Approach

State the concrete gains.

Good pattern:

- The direct payoff of this approach is...
- It helps maintainability, reuse, performance, or readability by...
- It reduces this class of problems...

### 4. What Else Could Be Done

Provide at least one realistic alternative.

Good pattern:

- Another reasonable option here would be...
- If the project size or team context were different, we might choose...

### 5. Why the Alternative Is Not Preferred Here

Compare honestly. Do not pretend one approach is universally best.

Good pattern:

- That approach is valid, but in this case...
- If we picked that option now, the tradeoff would be...
- Given the current complexity of the project, the better fit is...

### 6. How to Understand This Part

Turn the code or design into a mental model.

Good pattern:

- You can think of this as...
- At an abstract level, this layer is doing...
- From the perspective of data flow or responsibility flow, its real job is...

### 7. How to Explain It to Someone Else

Help the user describe it clearly to another learner or teammate.

Good pattern:

- If you want to explain this clearly, start with...
- A clearer way to describe it is...
- Do not start with code details. Start with the problem it solves, then explain the implementation.

## Short Output Format

For smaller modules, compress the explanation into this format:

- `What it does`:
- `Why this design`:
- `Benefits`:
- `Alternative`:
- `Why not the alternative`:
- `How to understand it`:
- `How to explain it to someone else`:

## Long Output Format

For important modules, use this format:

### Module Role

### Design Reason

### Benefits of This Choice

### Alternative Options

### Why the Alternatives Are Not Preferred Here

### How to Understand It

### How to Explain It Clearly to Someone Else

## Explanation Quality Bar

The explanation is not good enough if it:

- only restates code line by line
- only says "this is more maintainable" without explaining why
- only gives textbook theory without tying it to this project
- avoids discussing tradeoffs
- cannot help the user retell the idea in simple words
