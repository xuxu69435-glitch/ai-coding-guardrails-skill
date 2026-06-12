# AI Coding Guardrails Skill

English | [简体中文](./README.zh-CN.md)

A lightweight AI coding skill for keeping code changes minimal, scoped, explicit, and verifiable.

## What is this?

AI Coding Guardrails Skill is a practical skill for guiding AI coding assistants to work with more discipline and less unnecessary complexity.

It is designed to help AI assistants:

* state assumptions before implementation
* prefer simple solutions
* make minimal necessary changes
* avoid unrelated refactors
* avoid over-engineering
* define clear success criteria
* verify changes with tests or checks

## Why this skill exists

AI coding assistants are powerful, but they can easily create problems in real engineering workflows.

Common issues include:

* making hidden assumptions
* changing unrelated files
* refactoring code that was not part of the request
* adding unnecessary abstractions
* overcomplicating simple tasks
* skipping verification
* producing large diffs that are hard to review

This skill adds a set of practical guardrails to keep AI-generated code changes focused, intentional, and reviewable.

## Core principles

### 1. Think before coding

Before implementing, the AI should state its assumptions clearly.

If the request is ambiguous, the AI should surface the ambiguity instead of silently choosing one interpretation.

### 2. Simplicity first

The AI should write the minimum amount of code needed to solve the requested problem.

It should not add speculative features, unnecessary abstractions, or configurability that was not requested.

### 3. Surgical changes

The AI should touch only the code that is directly relevant to the task.

It should not perform drive-by refactors, unrelated cleanups, formatting changes, or improvements outside the requested scope.

Every changed line should trace back to the user’s request.

### 4. Goal-driven execution

Every coding task should be converted into a verifiable goal.

Examples:

* Bug fix: reproduce the issue, apply the smallest fix, then verify it.
* Feature change: define expected behavior, implement it, then check it.
* Refactor: confirm behavior before and after the change.

## When to use this skill

Use this skill when asking an AI assistant to:

* modify code
* add a feature
* fix a bug
* refactor existing code
* review an implementation plan
* keep changes small and reviewable
* avoid over-engineering
* avoid unrelated code changes
* explain assumptions before coding
* provide verification steps after coding

## When not to use this skill

This skill may not be ideal for:

* open-ended architecture exploration
* large-scale rewrites
* broad product ideation
* experimental prototyping with unclear goals
* tasks where wide-ranging creativity is more important than strict scope control

For exploratory work, it may be better to brainstorm freely first, then use this skill once the implementation goal is clear.

## Repository structure

```text
.
├── SKILL.md
├── README.md
├── README.zh-CN.md
└── LICENSE
```

* `SKILL.md`: the main skill definition
* `README.md`: English documentation
* `README.zh-CN.md`: Simplified Chinese documentation
* `LICENSE`: open-source license

## Usage

Add the contents of `SKILL.md` to any AI coding tool that supports skills, rules, custom instructions, project instructions, or project-level guidance.

This skill is suitable for workflows involving:

* ChatGPT
* Claude
* Cursor
* Windsurf
* Claude Code
* other AI coding agents or developer tools

Configuration details may vary by tool, but the goal is the same:

Make the AI follow the rules in `SKILL.md` when working on code-related tasks.

## Example prompts

You can use prompts like:

```text
Please follow the AI Coding Guardrails Skill:
- state assumptions first
- make only the minimum necessary changes
- avoid drive-by refactors
- explain how to verify the result
```

Or:

```text
Use the AI Coding Guardrails Skill to fix this bug.
First identify the likely cause, then make a minimal fix, and finally provide verification steps.
```

## Design philosophy

AI coding assistants should not default to broad rewrites, speculative abstractions, or unrelated improvements.

A good AI coding collaborator should:

* understand the request
* state assumptions
* control scope
* keep diffs reviewable
* verify the result

This skill is not about making AI write more code.

It is about making AI write less code, more precisely, with clearer reasoning and better verification.

## License

MIT
