# About me

  I build production systems around LLMs and set up agentic development in teams. The rule I work by: model output is untrusted. Side
  effects run in Go code after deterministic validation and an LLM critic, never straight from the model. Backend is the base under that 
  Go in production, industrial telemetry and IoT, Telegram bots, payment and LLM integrations. Engineering degree in power systems
  (NSTU, MSc in intelligent power plants and substations) and three years as an engineer before I moved to development.

  The AI side is not only my own code: I introduced AI-assisted development in a team from scratch - the process from spec to release,
  review and verification gates, agent skills for routine work, MCP integrations with internal systems.

  ## Projects

  **[transcrib](https://github.com/daniil4545/transcrib)** - Telegram bot that turns an online meeting (Zoom, Meet, Telemost) into a
  speaker-labeled transcript and an AI summary with action items. Live in production, subscriptions through YooKassa.
  Inside: PostgreSQL as the queue (FOR UPDATE SKIP LOCKED, no broker), job state machine, idempotent payments, 55% of the codebase is
  tests.

  **[tg-intake](https://github.com/daniil4545/tg-intake)** - intake agent: a multimodal model reads voice messages and screenshots, a
  round-based interview turns raw feedback into a usable description, the ticket goes to GitHub Issues. Second mode answers from the
  repository docs with a link to the source.
  Inside: a model per pipeline step instead of one for everything (multimodal for attachments, prefix-cached chat model for the
  interview), PostgreSQL as the queue, OpenRouter, GitHub REST API.

  **[ccnotify](https://github.com/daniil4545/ccnotify)** - macOS notifications for Claude Code session events; a click brings you back
  to that exact session.
  Inside: runs on agent hooks, tells apart end of turn, permission request and waiting for input, quiet rules to cut the noise, parallel
  sessions kept apart by a lock on the state file. Go, MIT, releases via GitHub Actions.

  **[ai-dev-digest](https://github.com/daniil4545/ai-dev-digest)** - daily AI/dev digest from 13 sources, scored by a local LLM
  (Ollama).
  Inside: per-source failure isolation, heuristic fallback when the model is unavailable, cross-run dedup in SQLite.

  **[modbus-emulator](https://github.com/daniil4545/modbus-emulator)** - Modbus device emulator for integration testing of industrial
  gateways without hardware.
  Inside: three transports (Modbus TCP, RTU-over-TCP, serial RTU over PTY), device fleet generator from a template, simulated register
  dynamics.

  ## Stack

  LLM in production (tool calling, structured output via JSON Schema, guardrails, eval harness, cost control per pipeline step), agentic
  development (Claude Code, Codex CLI, MCP, spec-driven process, verification gates), Go (goroutines, channels, pgx/v5, table-driven
  tests), PostgreSQL, ClickHouse, SQLite, MQTT, Modbus, Kafka, Docker, Kubernetes and Helm, GitHub Actions, GitLab CI. Python as a
  secondary language.

  ## Contacts

  Telegram [@dasukhar](https://t.me/dasukhar), email daniilsukhar@gmail.com
