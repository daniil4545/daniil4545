# About me

I build production systems around LLMs and set up agentic development in teams. The rule I work by: model output is untrusted. Side effects run in Go code after deterministic validation and an LLM critic, never straight from the model. Backend is the base under that: Go in production, industrial telemetry and IoT, Telegram bots, payment and LLM integrations. Engineering degree in power systems (NSTU, MSc in intelligent power plants and substations) and three years as an engineer before I moved to development.

The AI side is not only my own code: I introduced AI-assisted development in a team from scratch - the process from spec to release, review and verification gates, agent skills for routine work, MCP integrations with internal systems.

## Projects

**[transcrib](https://github.com/daniil4545/transcrib)** - Telegram bot that turns an online meeting (Zoom, Meet, Telemost) into a speaker-labeled transcript and an AI summary with action items. Live in production, subscriptions through YooKassa.  
Inside: PostgreSQL as the queue (FOR UPDATE SKIP LOCKED, no broker), job state machine, idempotent payments, 55% of the codebase is tests.

**[tg-intake](https://github.com/daniil4545/tg-intake)** - intake agent: a multimodal model reads voice messages and screenshots, a round-based interview turns raw feedback into a usable description, the ticket goes to GitHub Issues. Second mode answers from the repository docs with a link to the source.  
Inside: a model per pipeline step instead of one for everything (multimodal for attachments, prefix-cached chat model for the interview), PostgreSQL as the queue, OpenRouter, GitHub REST API.

**[tg-agent-mcp](https://github.com/daniil4545/tg-agent-mcp)** - MCP server that gives a Claude Code agent hands in Telegram: find a person, write, read a dialog, run a campaign over a ready recipient list.  
Inside: pacing, send window and daily cap live in PostgreSQL, so a restart cannot bypass them; one message per person across campaigns; a Telegram flood limit stops the account until a human resumes it; a second agent token only reaches an allow-list. Go, MTProto, official MCP go-sdk.

**[modbus-emulator](https://github.com/daniil4545/modbus-emulator)** - Modbus device emulator for integration testing of industrial gateways without hardware.  
Inside: three transports (Modbus TCP, RTU-over-TCP, serial RTU over PTY), device fleet generator from a template, simulated register dynamics.

## Stack

LLM in production (tool calling, structured output via JSON Schema, guardrails, eval harness, cost control per pipeline step), agentic development (Claude Code, Codex CLI, MCP, spec-driven process, verification gates), Go (goroutines, channels, pgx/v5, table-driven tests), PostgreSQL, ClickHouse, SQLite, MQTT, Modbus, Kafka, Docker, Kubernetes and Helm, GitHub Actions, GitLab CI. Python as a secondary language.

## Contacts

Telegram [@dasukhar](https://t.me/dasukhar), email daniilsukhar@gmail.com
