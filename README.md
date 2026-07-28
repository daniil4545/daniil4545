# Даниил Сухар

Go backend-разработчик с инженерным образованием в энергетике (НГТУ, интеллектуальные электрические станции). Строю production-сервисы: промышленная телеметрия и IoT, Telegram-боты, платёжные и LLM-интеграции. Отдельное направление - AI-engineering: проектирую LLM-пайплайны, где модель не имеет прямого доступа к side effects, внедряю AI-ассистированную разработку в командах.

## Проекты

**[transcrib](https://github.com/daniil4545/transcrib)** - Telegram-бот: превращает онлайн-встречу (Zoom, Meet, Телемост) в транскрипт по спикерам и AI-конспект с задачами. Живой прод с подпиской через ЮKassa.
Внутри: PostgreSQL как очередь (FOR UPDATE SKIP LOCKED, без брокера), state machine джобы, идемпотентные платежи, 55% кодовой базы - тесты.

**[modbus-emulator](https://github.com/daniil4545/modbus-emulator)** - эмулятор Modbus-устройств для интеграционного тестирования промышленных шлюзов без железа.
Внутри: три транспорта (Modbus TCP, RTU-over-TCP, serial RTU через PTY), генератор парка устройств из шаблона, симуляция динамики регистров.

**[go-grocer](https://github.com/daniil4545/go-grocer)** - Telegram-бот учёта покупок: принимает фото QR-кода чека, получает позиции через API ФНС, считает статистику в SQLite.
Внутри: pure Go без CGO (modernc.org/sqlite), retry-протокол внешнего API, деньги в копейках, table-driven тесты.

**[ai-dev-digest](https://github.com/daniil4545/ai-dev-digest)** - ежедневный дайджест AI/dev-новостей из 13 источников со скорингом локальной LLM (Ollama).
Внутри: изоляция сбоев источников, эвристический fallback при недоступности LLM, дедуп между запусками через SQLite.

## Стек

Go (goroutines, channels, pgx/v5, table-driven tests), PostgreSQL, ClickHouse, SQLite, MQTT, Modbus, Kafka, LLM-интеграции (tool calling, guard-слои, eval), Docker, Kubernetes и Helm, GitHub Actions, GitLab CI. Вторичный язык Python.

## Контакты

Telegram [@dasukhar](https://t.me/dasukhar), email daniilsukhar@gmail.com
