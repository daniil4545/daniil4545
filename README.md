# About me

I build production systems around LLMs, from cloud APIs to local models on the customer's own hardware, and set up agentic development in teams. The rule I work by: model output is untrusted. Side effects run in Go code after deterministic validation and an LLM critic, never straight from the model. Backend is the base under that: Go in production, industrial telemetry and IoT, Telegram bots, payment and LLM integrations. Engineering degree in power systems (NSTU, MSc in intelligent power plants and substations) and three years as an engineer before I moved to development.

The AI side is not only my own code: I introduced AI-assisted development in a team from scratch - the process from spec to release, review and verification gates, agent skills for routine work, MCP integrations with internal systems.

## Projects

**[tix](https://github.com/daniil4545/tix)** - task tracker for AI coding agents: markdown tasks under git in one folder, agents (Claude Code, Codex) work through a CLI, a person steers on a terminal board. Every edit is a commit that names the agent session and model behind it, and a comment on a task reaches the agent that holds it.  
Inside: lock, temp file and rename for safe writes, a 3-hour claim on a task, a short context brief for agents under 2000 characters, hooks for Claude Code and Codex, TUI. Go, CI on macOS and Linux, v0.1.0 with binaries.

**[transcrib](https://github.com/daniil4545/transcrib)** - Telegram bot that turns an online meeting (Zoom, Meet, Telemost) into a speaker-labeled transcript and an AI summary with action items. Live in production, subscriptions through YooKassa.  
Inside: PostgreSQL as the queue (FOR UPDATE SKIP LOCKED, no broker), job state machine, idempotent payments, 55% of the codebase is tests.

**[lead-qualifier](https://github.com/daniil4545/lead-qualifier)** - lead qualification engine on an LLM agent: the model talks to the lead and calls tools, Go validates every step before any side effect, a critic checks replies, qualified leads book a meeting. Built from a production service, with the client's data replaced by a fictional company.  
Inside: tool calling with strict JSON Schema, deterministic decision rules and guardrails with a test per rule, state and outbox in PostgreSQL, business data in a catalog directory (a second catalog passes the same tests without code changes), offline golden dialogs and a prompt eval runner. Go, console demo.

**[tg-agent-mcp](https://github.com/daniil4545/tg-agent-mcp)** - MCP server that gives a Claude Code agent hands in Telegram: find a person, write, read a dialog, run a campaign over a ready recipient list.  
Inside: pacing, send window and daily cap live in PostgreSQL, so a restart cannot bypass them; one message per person across campaigns; a Telegram flood limit stops the account until a human resumes it; a second agent token only reaches an allow-list. Go, MTProto, official MCP go-sdk.

**[pii-scrub](https://github.com/daniil4545/pii-scrub)** - replaces personal data in Russian text with stable labels before it reaches a model, including phone numbers and e-mails a speech recognizer writes out as words.  
Inside: Natasha NER with a morphology filter, rules for dictated digits interrupted by replies, and a closed failure: leftover digits make the tool refuse instead of passing the text on. Python, CI, v0.1.0.

**[modbus-emulator](https://github.com/daniil4545/modbus-emulator)** - Modbus device emulator for integration testing of industrial gateways without hardware.  
Inside: three transports (Modbus TCP, RTU-over-TCP, serial RTU over PTY), device fleet generator from a template, simulated register dynamics.

## Tools for agentic development

Small tools I wrote for my own work with coding agents and keep using.

- **[ccnotify](https://github.com/daniil4545/ccnotify)** - macOS notifications for Claude Code sessions: names the project and the event, a click returns to the right window. Go, no dependencies, v0.1.0.
- **[envkey](https://github.com/daniil4545/envkey)** - Claude Code plugin: the agent lists, uses, adds and removes `.env` variables by name and never sees the values; a hook blocks direct access to the file. Python.

## Stack

LLM in production (tool calling, structured output via JSON Schema, guardrails, eval harness, cost control per pipeline step), agentic development (Claude Code, Codex CLI, MCP, spec-driven process, verification gates), Go (goroutines, channels, pgx/v5, table-driven tests), PostgreSQL, ClickHouse, SQLite, MQTT, Modbus, Kafka, Docker, Kubernetes and Helm, GitHub Actions, GitLab CI. Python (FastAPI, Pydantic, pytest) for services around local models and speech recognition.

## Contacts

Telegram [@dasukhar](https://t.me/dasukhar), email daniilsukhar@gmail.com
