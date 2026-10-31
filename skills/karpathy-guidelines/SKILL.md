---
name: karpathy-guidelines
description: Keep coding and refactoring focused on the requested outcome, a demonstrated root cause, minimal coherent changes, and meaningful verification.
license: MIT
---

# Karpathy Guidelines

Behavioral guidance derived from Andrej Karpathy's observations on LLM coding
pitfalls. Use judgment proportional to the task; this is not a fixed workflow.

## Understand the outcome

Inspect the relevant code, callers, and contract. Surface assumptions that could
change the result. Ask about material ambiguity or product tradeoffs; resolve
routine implementation details within the user's authorization.

## Solve the cause with a coherent change

Trace an incorrect result to its source before choosing the fix. Consider
deletion, consolidation, or correcting ownership before adding compensating
checks. Validate where an invariant belongs or untrusted data enters; additional
layers need an independent reason.

Include necessary restructuring and remove workarounds or code made obsolete by
the fix. Avoid unrelated cleanup. Match local conventions where they serve the
task. Do not add speculative features, single-use abstractions, configurability,
or handling for impossible scenarios.

## Verify behavior and usefulness

Define what observable outcome would establish success. Reuse adequate tests;
add focused regressions for important failures and boundaries otherwise missed.
A new function or doc edit alone does not require another test. Exercise real
behavior rather than mirroring private implementation or checking names alone.

Use a focused failing reproduction when it helps establish the defect. Existing
coverage and appropriate direct checks can suffice for refactoring or low-impact
changes. Do not delete correct work merely because a test was not written first.

Run checks appropriate to the change, inspect their actual output, and report
material limits. Scale planning and review to risk. A bounded task can use a
short approach in chat; stop expanding verification when the outcome is proved
and no new concern remains.
