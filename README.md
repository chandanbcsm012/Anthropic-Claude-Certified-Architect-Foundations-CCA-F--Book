# Anthropic Claude Certified Architect Foundations (CCA-F)

**CCA-F (Claude Certified Architect – Foundations)** is Anthropic's foundational certification for engineers and architects who design, build, and operate production systems on top of Claude — spanning agentic orchestration, tool and MCP (Model Context Protocol) design, workflow configuration, prompt engineering, and context reliability. This book is a study guide and field reference for anyone preparing for the CCA-F exam, from developers building their first Claude-powered agent to architects reviewing multi-agent systems already in production. It is organized into **5 exam domains spanning 19 chapters**: 18 content chapters that build the domains one concept at a time, plus a closing appendix chapter for revision and exam-day practice.

## How to Use This Book

- **Read Chapters 1–18 sequentially.** Each domain builds on the one before it — later chapters routinely assume you've internalized ideas from earlier ones (for example, Chapter 18's error context builds directly on Chapter 6's failure classification), so working through them in order is the most reliable path.
- **Use Chapter 19 as an ongoing reference, not just a finale.** Its revision notes, glossary, acronym list, architecture diagrams, and cheat sheets are useful to revisit while you're still working through Chapters 1–18, not only at the end.
- **Save the mock exam for last.** Chapter 19's 50-question mock exam is meant to be taken as a timed dress rehearsal after finishing Chapter 18 — one full pass under exam conditions, then a return trip to whichever chapter each missed question traces back to.
- **Keep the domain structure in mind.** The exam blueprint is organized into 5 domains, and this book mirrors that structure directly (see the Table of Contents below), so you always know which domain a chapter's material will be scored under.

## Table of Contents

### Domain 1: Agentic Architecture and Orchestration (Chapters 1–4)

- [Chapter 1: The Agentic Loop](./chapter-01-the-agentic-loop.md) — the four-stage loop (compose and send, model responds, inspect `stop_reason`, act and feed back) that turns a single stateless model call into a sustained, goal-directed agent.
- **Chapter 2:** [The Hub-and-Spoke Model](./chapter-02-the-hub-and-spoke-model.md) — how multi-agent systems coordinate through a central coordinator that decomposes, delegates to, and reassembles work from specialized subagents.
- **Chapter 3:** [The Agent Tool, Parallel Execution, and the Stakes-Proportionate Rule](./chapter-03-the-agent-tool-parallel-execution-and-the-stakes-proportionate-rule.md) — configuring the agent tool and `allowedTools`, choosing parallel vs. sequential subagent execution, and calibrating caution to risk.
- **Chapter 4:** [Programmatic Control and Hooks](./chapter-04-programmatic-control-and-hooks.md) — gates and PreToolUse/PostToolUse hooks that enforce rules at the system level, independent of what the model decides.

### Domain 2: Tool Design and MCP Integration (Chapters 5–8)

- **Chapter 5:** [Tool Descriptions](./chapter-05-tool-descriptions.md) — how Claude selects between tools and the five-element framework for writing descriptions that route correctly every time.
- [Chapter 6: Error Handling Patterns](./chapter-06-error-handling-patterns.md) — sorting tool and MCP failures into distinct categories and designing error responses Claude can act on without a human in the loop.
- [Chapter 7: MCP Configuration](./chapter-07-mcp-configuration.md) — project-level vs. user-level MCP configuration, precedence rules, and a four-step process for diagnosing a missing server.
- **Chapter 8:** [Tool Scoping and Agent Roles](./chapter-08-tool-scoping-and-agent-roles.md) — why tool count degrades selection accuracy and how to right-size an agent's toolset to roughly 10–20 tools.

### Domain 3: Configuration and Workflow Organization (Chapters 9–12)

- **Chapter 9:** [The CLAUDE.md Hierarchy](./chapter-09-the-claude-md-hierarchy.md) — the project, directory, user, and managed scopes of CLAUDE.md, load order, and diagnosing conventions that exist on paper but aren't applied.
- **Chapter 10:** [Agent Skills](./chapter-10-agent-skills.md) — on-demand specialized know-how, the SKILL.md structure, and choosing between a skill, a hook, a subagent, and an MCP server.
- **Chapter 11:** [Path-Specific Rules and Context Fork](./chapter-11-path-specific-rules-and-context-fork.md) — isolating a skill's execution in its own subagent and applying file-pattern-based rules to protect the context window.
- **Chapter 12:** [CLI Flags and CI/CD](./chapter-12-cli-flags-and-ci-cd.md) — the `-p` flag and companion flags that make Claude Code a reliable building block inside CI/CD pipelines.

### Domain 4: Prompt Engineering and Structured Output (Chapters 13–15)

- **Chapter 13:** [Match Criteria and Few-Shot Examples](./chapter-13-match-criteria-and-few-shot-examples.md) — writing explicit match criteria instead of vague confidence instructions and using few-shot examples to make output consistent.
- **Chapter 14:** [JSON Schema and Structured Output](./chapter-14-json-schema-and-structured-output.md) — using `tool_use` with JSON Schema to guarantee well-formed output, and the fabricated-data problem schema alone can't solve.
- **Chapter 15:** [API Selection: Cost vs. Latency](./chapter-15-api-selection-cost-vs-latency.md) — choosing between the Synchronous and Batch APIs and reasoning through the cost-versus-latency tradeoff.

### Domain 5: Context Management and Reliability (Chapters 16–18)

- **Chapter 16:** [Context Window Management](./chapter-16-context-window-management.md) — why progressive summarization quietly erodes precision, protecting facts that can't afford to drift, and keeping tool output from drowning out what matters.
- **Chapter 17:** [Escalation Triggers](./chapter-17-escalation-triggers.md) — the three valid escalation triggers, and why reacting to tone or difficulty alone are not valid triggers.
- [Chapter 18: Error Context and Common Mistakes](./chapter-18-error-context-and-common-mistakes.md) — structured error context for coordinators, fallback paths, and the retry anti-pattern of hiding failures until every attempt is burned.

### Appendix

- **Appendix:** [Exam Prep & Reference Appendix](./chapter-19-exam-prep-and-appendix.md) — revision notes for all 18 chapters, glossary, acronym list, architecture diagrams, cheat sheets, consolidated best practices, exam-day tips, and a 50-question mock exam.

## A Note on Images

Chapters 1-7 include real diagrams (`images/ch01-img01.jpg` through `ch07-img02.jpg`) recovered from the original course material. Chapters 8-18 use hand-authored SVG diagrams (`images/ch08-img01.svg` through `ch18-img04.svg`) built to match each figure's caption, since no source diagrams existed for those chapters. Every figure in the book now resolves to a real image file.
