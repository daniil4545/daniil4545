# Даниил Сухар

Go backend-разработчик с инженерным бэкграундом в энергетике (НГТУ, интеллектуальные электрические станции). Строю production-сервисы: телеметрия и IoT, Telegram-боты, интеграции с платёжными и LLM API. Отдельное направление — AI-engineering: проектирую пайплайны с LLM, где модель не имеет прямого доступа к side effects, и внедряю AI-ассистированную разработку в командах.

## Проекты

- **[transcrib](https://github.com/daniil4545/transcrib)** — Telegram-бот: онлайн-встреча (Zoom/Meet/Телемост) -> транскрипт по спикерам и AI-конспект с задачами. Живой прод с подпиской через ЮKassa.
  Внутри: PostgreSQL как очередь (`FOR UPDATE SKIP LOCKED`, без брокера), state machine джобы с guard-переходами, идемпотентные платежи, 55% кодовой базы — тесты.
- **[modbus-emulator](https://github.com/daniil4545/modbus-emulator)** — эмулятор Modbus-устройств для интеграционного тестирования промышленных шлюзов без железа.
  Внутри: три транспорта (Modbus TCP, RTU-over-TCP, serial RTU через PTY), генератор парка устройств из шаблона, симуляция динамики регистров.
- **[go-grocer](https://github.com/daniil4545/go-grocer)** — Telegram-бот учёта покупок: QR-код чека -> данные ФНС -> SQLite-статистика.
  Внутри: pure Go без CGO (modernc.org/sqlite), retry-протокол внешнего API, деньги в копейках, table-driven тесты.
- **[ai-dev-digest](https://github.com/daniil4545/ai-dev-digest)** — ежедневный дайджест AI/dev-новостей из 13 источников со скорингом локальной LLM (Ollama).
  Внутри: изоляция сбоев источников, эвристический fallback при недоступности LLM, дедуп между запусками через SQLite.

## Стек

Go (goroutines, channels, pgx/v5, table-driven tests) · PostgreSQL · ClickHouse · SQLite · MQTT · Modbus · Kafka · LLM-интеграции (tool calling, guard-слои, eval) · Docker · Kubernetes/Helm · CI (GitHub Actions, GitLab CI) · Python

## Контакты

Telegram: [@dasukhar](https://t.me/dasukhar) · Email: daniilsukhar@gmail.com
