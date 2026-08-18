# Claude Opus 5 guidance

Updated: 2026-07-26

Read this reference only when optimizing a complex agentic, coding, research, long-context, document, or migration-derived prompt. The core Skill contains the default behavior.

## Stable design judgments

Opus 5 performs best when given the complete task specification and room to act. Specify the result, scope, context, constraints, permissions, and output shape; avoid manually scripting its reasoning.

Opus 5 verifies and self-corrects without prompting. Legacy instructions such as “double-check everything,” mandatory final verification, or “use a subagent to verify” compound its native behavior and waste tokens. Request a concrete validation operation only when that operation is part of the deliverable, such as running a named test suite after changing code.

Opus 5 may widen scope. For narrow work, state what is in scope, what is outside it, which routine judgments it may make, and which materially different interpretations require confirmation.

Opus 5 delegates readily. Allow subagents only for independent, sizeable tracks that benefit from isolated context or parallel work. Do not use delegation as a generic quality signal or self-check.

Visible verbosity and reasoning depth are different controls. State the desired answer or document length directly. Written deliverables tend to run long, so request enough substance without filler or repeated summaries.

Context is a finite attention budget even with a large context window. Prefer high-signal context, just-in-time retrieval, lightweight references, progressive disclosure, and compact state over loading every rule and document up front.

Examples remain useful for taste or exact format, but too many examples can constrain exploration. Prefer a small set of canonical examples only when natural-language criteria are insufficient.

XML tags and Markdown headings are separators, not quality talismans. Use them only when a prompt contains distinct information classes that could otherwise be confused.

## Chat-product boundary

This Skill targets claude.ai and Claude desktop or mobile chat products. Do not surface API-only configuration such as model strings, effort values, thinking fields, sampling parameters, prompt caching, beta headers, or tool schemas.

The official migration guide says adaptive thinking is on by default for Opus 5. That strengthens the case for removing old thinking-trigger phrases from chat prompts.

## Model-specific failure checks

When the requested task is narrow, check for scope expansion.

When the task is agentic, check for unnecessary progress narration and uncontrolled delegation.

When the deliverable is a report or file, check for unbounded length and boilerplate.

When adapting an older prompt, check for repeated verification, forced chain-of-thought, fixed agent counts, copied examples that restrict exploration, and duplicated instructions.

When the task is code review, preserve finding coverage. Opus 5 has strong precision and recall, but literal filters such as “only report important issues” can suppress valid findings.

## Official sources

Anthropic, “Prompting Claude Opus 5”: https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/prompting-claude-opus-5

Anthropic, “Prompting best practices”: https://platform.claude.com/docs/en/build-with-claude/prompt-engineering/claude-prompting-best-practices

Anthropic, “Migration guide”: https://platform.claude.com/docs/en/about-claude/models/migration-guide

Anthropic, “The new rules of context engineering for Claude 5 generation models”: https://claude.com/blog/the-new-rules-of-context-engineering-for-claude-5-generation-models

Anthropic Engineering, “Effective context engineering for AI agents”: https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents
