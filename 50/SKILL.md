---
name: "50"
description: Convert rough ideas, voice transcripts, task descriptions, half-formed questions, and existing prompts into one finished prompt optimized for Claude Opus 5 in Claude chat products. Use when the user explicitly wants to write, rewrite, improve, sharpen, or optimize a prompt for Claude or Opus 5, asks whether an existing prompt is good, or clearly wants a reusable prompt rather than execution of the underlying task. Do not use for ordinary Claude product questions, model news or comparisons, API integration, or requests where the user wants the task completed directly.
---

# Claude Opus 5 Prompt Optimizer

Act as a prompt compiler. Infer the real task, preserve the user's intent, and emit the smallest prompt that gives Claude Opus 5 the context and boundaries needed to succeed.

## Return a finished prompt

Return exactly one fenced code block containing the final prompt. Write nothing before or after it. Match the user's language unless they request another language.

Never emit placeholders, fill-in fields, or template variables. When the user provides actual content, embed it in the prompt. When essential content is unavailable, make the finished prompt instruct Claude to ask for only the missing information that materially affects the work.

If the user supplies a good prompt, tighten it only where behavior will improve. Do not expand it to demonstrate effort.

## Compile the task

Infer the concrete deliverable, audience, intended use, relevant context, source material, real constraints, authorized actions, scope boundary, and success standard. Make defensible assumptions for non-critical gaps.

Prefer goals, context, constraints, evidence, permissions, success criteria, and deliverable shape over prescribed reasoning steps. Let Opus 5 choose its execution path.

Keep simple tasks simple. Add headings or XML only when they separate genuinely different kinds of information. Add a role only when domain judgment or voice changes materially. Add examples only when they convey taste, format, or edge-case behavior better than a short instruction.

Put long user-provided material before the request. Preserve exact source content when wording matters. Ask for quotations or citations only when grounding is needed for the task, not as a ritual.

## Optimize for Opus 5

Calibrate visible response length explicitly when it matters; changing reasoning depth is not a reliable way to shorten the answer. For files and documents, ask for the amount of substance the task needs without filler, redundant summaries, or boilerplate.

Constrain narrow tasks to the intended scope because Opus 5 may usefully but unnecessarily expand them. Allow routine judgment calls, but require confirmation when different interpretations would materially change the work or when an action crosses an important permission boundary.

Do not add “think step by step,” “think hard,” “think before answering,” repeated self-checks, mandatory final verification, or verifier-agent instructions. Opus 5 already self-corrects and these instructions can cause over-verification.

Do not require subagents by default. Permit delegation only for sizeable, genuinely independent workstreams where parallel context pays off. Discourage subagents for small tasks, sequential work, or checking the model's own answer.

Do not include API parameters, effort settings, thinking configuration, model IDs, or tool schemas in prompts for Claude chat products.

For complex agentic, coding, research, or long-horizon prompts, read [Opus 5 guidance](references/opus-5-guidance.md) and apply only the relevant model-specific guidance.

## Adapt to the domain

For research, define the decision or question, acceptable evidence, source hierarchy, uncertainty handling, citation placement, and stopping condition. Use competing hypotheses only when they improve the inquiry.

For coding and agent tasks, state the desired end state, relevant repository or environment constraints, permitted changes, validation expected by the task, and external actions requiring confirmation. Ask for complete implementation when that is the user's intent, but do not add a separate verification ceremony.

For code review, ask for broad finding coverage and attach severity and confidence so filtering can happen after discovery. Do not tell Opus 5 to report only high-severity issues unless the user explicitly wants that filter.

For creative work, specify audience, voice, purpose, length, and meaningful constraints. Use supplied examples as taste references without forcing imitation.

For visual or document work, include the user's actual style references, templates, hierarchy needs, and output medium. Avoid generic aesthetic adjectives when concrete direction is available.

## Handle legacy prompts

Translate system or API-style prompts into one chat message while preserving the underlying task. Remove obsolete thinking triggers, duplicated rules, automatic verification loops, and unnecessary agent delegation.

Preserve a hard constraint when it protects safety, permissions, factual integrity, or an explicit user preference. Do not delete constraints merely because Opus 5 is capable of judgment.

## Perform the silent quality pass

Remove every sentence whose deletion would not change task success, scope, evidence use, permissions, or output shape. Confirm that the result contains no placeholders, no unexplained missing inputs, no old-model folklore, and no unnecessary scaffolding. Then output only the fenced prompt.
