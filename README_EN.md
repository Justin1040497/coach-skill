<div align="center">
  <img src="./assets/coach-icon.png" alt="Coach" width="120" />
  <h1>Coach</h1>
  <p><strong>A coach-style skill for learning projects and real engineering growth</strong></p>
  <p>Help AI guide thinking, planning, correction, and explanation before it accelerates implementation.</p>

  <p>
    <img alt="version" src="https://img.shields.io/badge/version-v1.0-111827?style=for-the-badge" />
    <img alt="mode" src="https://img.shields.io/badge/mode-Coach-2563EB?style=for-the-badge" />
    <img alt="focus" src="https://img.shields.io/badge/focus-Learning%20Projects-F59E0B?style=for-the-badge" />
    <img alt="language" src="https://img.shields.io/badge/language-Adaptive-16A34A?style=for-the-badge" />
  </p>

  <p>
    <img alt="workflow" src="https://img.shields.io/badge/workflow-Think%20First-7C3AED?style=flat-square" />
    <img alt="ownership" src="https://img.shields.io/badge/ownership-User%20Led-DC2626?style=flat-square" />
    <img alt="acceleration" src="https://img.shields.io/badge/AI-Low--Leverage%20Acceleration-0891B2?style=flat-square" />
    <img alt="practice" src="https://img.shields.io/badge/review-Post--Completion%20Teaching-65A30D?style=flat-square" />
  </p>
</div>

---

`Coach` is a skill for learning projects, portfolio projects, internship projects, campus recruitment projects, and competition projects.

Its purpose is not to finish the project for the user as fast as possible. Its purpose is to help the user learn in a real engineering context:

- think before building
- understand before implementing
- keep high-leverage work user-owned
- let AI accelerate low-leverage repetitive work
- explain clearly what was built and why

## Core Positioning

`Coach` is designed for cases where:

- the user wants to build a project without letting AI ghostwrite everything
- the user wants AI to guide thinking about architecture, business flow, component boundaries, performance, code quality, coupling, and reuse
- the user wants corrections based on real engineering practice and strong open-source patterns
- the user wants post-completion explanations so the work is genuinely understood and can be explained to others

## Quick Start

Recommended usage flow for `Coach`:

1. tell AI your project goal, current progress, and exact blocking point
2. explicitly ask for coach-style guidance instead of direct completion
3. if you want a broader plan, use AI to review it and define user-vs-AI ownership
4. complete the key step yourself, then ask AI to review, correct, and explain it

Examples:

```text
Use $Coach to help me build this learning project step by step.
I want to own the architecture and core business flow myself.
First help me review my plan instead of writing the code directly.
```

```text
Use $Coach to review the module I just finished.
Explain what it does, why it is designed this way, what alternatives exist,
and how I should understand and explain it clearly to someone else.
```

## Example Usage

Typical requests:

- “Do not write the code yet. Help me review whether this project plan is reasonable.”
- “I want to write this module myself. Break it into a few steps for me.”
- “I just finished this part. Help me understand what it is actually doing.”
- “Review this learning project and tell me what looks like real engineering work and what looks too AI-assembled.”

## What It Does

- listens to the user's own plan first
- corrects weak architecture, ownership, and engineering decisions
- builds and saves a project plan only when the user explicitly wants that
- clearly separates:
  - work the user must complete personally
  - work where AI may guide only
  - work where AI is recommended to accelerate
  - repetitive work AI may complete directly
- after the user completes a module, explains:
  - what it does
  - why it is designed this way
  - what benefits it brings
  - what other options exist
  - why those options are not preferred here
  - how to understand it clearly
  - how to explain it clearly to someone else

## Core Principles

- understanding before speed
- user ownership before AI substitution
- one meaningful next step at a time
- questions, hints, checkpoints, and scaffolds before full answers
- feedback anchored to the user's actual code and current attempt
- corrections grounded in real engineering practice instead of textbook-only explanations

## Language Behavior

- prompt wording, coaching questions, reviews, and explanations should follow the user's working language
- if the user mainly uses Chinese, respond in Chinese
- if the user mainly uses English, respond in English
- if the user mixes languages, follow the main task language unless the user explicitly requests otherwise

## Good Trigger Examples

Examples:

- Guide me through this project step by step.
- Do not give me the full code yet. Help me clean up the plan first.
- Review the architecture of this learning project.
- I want to build the core modules myself. Help me plan and correct the structure.
- After I finish this part, explain what it is doing and why.

## File Structure

- `SKILL.md`: core skill rules and routing rules
- `agents/openai.yaml`: UI metadata, prompt, icon
- `references/planning.md`: project-level planning mode, including question flow, ownership labels, TDD guidance, and save rules
- `references/coaching.md`: current-task coaching mode for feature work, debugging, review, and post-completion explanation
- `references/review-checklist.md`: project review checklist
- `docs/plans/`: directory for saved plan markdown files after user confirmation

## Who It Is For

- students who want projects to build real ability
- developers who do not want to lose fundamentals to constant AI ghostwriting
- people who want projects they can ship, explain, and keep improving

## Chinese Readme

See [README.md](./README.md).
