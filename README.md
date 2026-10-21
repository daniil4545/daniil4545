# Daniil Sukhar

AI engineer: I put LLMs into business processes and build the tooling that lets coding agents ship production code under review.

I design the system, write the spec and accept the result; agents (Claude Code, Codex) write the code, and tests, linters and review gates decide what ships. Model output is untrusted: side effects run in code after deterministic checks. Before software I spent three years as an engineer in the power industry (MSc, NSTU), so I am used to systems that must not lose data.

## LLM in business processes

| Project | What it does | Stack |
|---|---|---|
| [lead-qualifier](https://github.com/daniil4545/lead-qualifier) | LLM agent that qualifies leads in chat and books a meeting; every tool call is validated in Go before any side effect, a critic checks replies, golden dialogs and a prompt eval runner | Go, PostgreSQL, tool calling, JSON Schema |
| [transcrib](https://github.com/daniil4545/transcrib) | Telegram bot: online meeting to speaker-labeled transcript and AI summary with action items, subscriptions through YooKassa | Go, PostgreSQL as a queue, state machine |
| [pii-scrub](https://github.com/daniil4545/pii-scrub) | Removes personal data from Russian text before it reaches a model, including numbers spoken as words; refuses when digits are left | Python, NER, eval set |

## Tools for agentic development

| Project | What it does | Stack |
|---|---|---|
| [tix](https://github.com/daniil4545/tix) | Task tracker for AI coding agents: markdown tasks under git, every edit a commit that names the agent session, a terminal board for the human | Go, TUI, CI on macOS and Linux |
| [tg-agent-mcp](https://github.com/daniil4545/tg-agent-mcp) | MCP server that gives an agent hands in Telegram, with send window and daily cap enforced in PostgreSQL | Go, MTProto, MCP |
| [envkey](https://github.com/daniil4545/envkey) | Claude Code plugin: the agent uses `.env` variables by name and never sees the values | Python |

## Stack

Python and Go, PostgreSQL, Docker, Kubernetes, GitHub Actions. LLM: tool calling, structured output, retrieval with source attribution, evals, local models (Ollama), speech recognition. Agentic development: Claude Code, Codex, MCP, spec-driven process with review gates.

## Contacts

Telegram [@dasukhar](https://t.me/dasukhar), email daniilsukhar@gmail.com
