---
name: ai-coding-guardrails-skill
description: >-
  Guides implementation with explicit assumptions, simplicity over speculation, surgical diffs only for the requested change, and verifiable success criteria (tests or checks before/after). Use when modifying code, adding features, fixing bugs, refactoring, reviewing a plan before coding, or when the user wants minimal scope, no drive-by refactors, or pushback on over-engineering. Also when the user mentions 写代码、改代码、加功能、修 bug、重构、最小改动、不要顺手重构、先澄清再写、可验证、别过度设计、范围要小、只改相关的.
---

# ai-coding-guardrails-skill

Use this skill to keep code work explicit, minimal, scoped, and verifiable.

## 1. Think Before Coding

Do not assume. Do not hide confusion. Surface tradeoffs.

Before implementing:

- State assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them; do not pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what is confusing. Ask.

## 2. Simplicity First

Write the minimum code that solves the problem. Add nothing speculative.

- No features beyond what was asked.
- No abstractions for single-use code.
- No flexibility or configurability that was not requested.
- No error handling for impossible scenarios.
- If 200 lines could be 50 lines, rewrite it.
- Ask: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

## 3. Surgical Changes

Touch only what is necessary. Clean up only the mess created by the current change.

When editing existing code:

- Do not improve adjacent code, comments, or formatting.
- Do not refactor things that are not broken.
- Match existing style, even if another style would be preferable.
- If unrelated dead code appears, mention it; do not delete it.

When the current change creates orphans:

- Remove imports, variables, and functions made unused by the current change.
- Do not remove pre-existing dead code unless asked.
- Every changed line should trace directly to the user's request.

## 4. Goal-Driven Execution

Define success criteria. Loop until verified.

Transform tasks into verifiable goals:

- "Add validation" -> write tests for invalid inputs, then make them pass.
- "Fix the bug" -> write a test that reproduces it, then make it pass.
- "Refactor X" -> ensure tests pass before and after.

For multi-step tasks, state a brief plan:

1. [Step] -> verify: [check]
2. [Step] -> verify: [check]
3. [Step] -> verify: [check]

Strong success criteria allow independent progress. Weak criteria such as "make it work" require clarification before coding.