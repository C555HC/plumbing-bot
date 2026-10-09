# Скиллы для дизайна, таблиц и разработки

Проверено: 8 октября 2026 года. Найденные инструкции прочитаны как материалы исследования. Ничего из внешних репозиториев не установлено и не активировано.

Скилл — инструкция для AI-агента, иногда со скриптами и ресурсами. Он помогает агенту выполнить задачу, но сам не становится таблицей, календарём или функциональностью CRM. Компоненты приложения перечислены [отдельно](ui-and-integrations.md).

Дополнение от 10 октября: [индивидуальные оценки применимости по десятибалльной шкале](skill-ratings.md).

## Подборка

| Навык / источник | Для чего пригодится | Лицензия проверенного материала | Оценка для проекта |
| --- | --- | --- | --- |
| Anthropic frontend-design | Визуальное направление, типографика, композиция интерфейса | Apache-2.0 в лицензии конкретного навыка | Использовать для экрана мастера и клиентской записи; доступный локальный frontend-design уже есть в каталоге Codex |
| Официальный shadcn skill | Работа с компонентами shadcn и конфигурацией проекта | MIT репозитория shadcn/ui | Самый предметный кандидат для компонентов и таблиц при выборе shadcn |
| Vercel web-design-guidelines | Проверка интерфейса по веб-рекомендациям и доступности | MIT по README репозитория | Полезен для проверки форм, фокуса, состояний и взаимодействий |
| Vercel react-best-practices | Производительность React/Next.js | MIT в метаданных навыка и README | Применять, если выберем соответствующий стек |
| Vercel composition-patterns | Организация повторно используемых React-компонентов | MIT в метаданных навыка | Полезен, когда появляются общие карточки, формы и действия |
| Impeccable | Дизайн, улучшение и аудит интерфейсов | Apache-2.0 | Альтернатива для системной работы с дизайном; автор описывает поддержку Codex и AntiGravity |
| UI UX Pro Max | Подбор палитр, шрифтов и UX-паттернов с ресурсами и скриптами | MIT | Дополнительный справочник для визуальных вариантов |
| Anthropic webapp-testing | Проверка веб-приложения через Playwright | Apache-2.0 в лицензии конкретного навыка | Кандидат для будущей проверки созданного интерфейса |

Таблица содержит предварительную оценку, а не выбранный набор обязательных зависимостей. Локальный навык Codex и опубликованный Anthropic frontend-design не проверялись на полное совпадение.

## Где брать: закреплённые первоисточники

- **frontend-design:** [SKILL.md](https://github.com/anthropics/skills/blob/683bc88e56f3e09ba94f7055977f3d3aa499f202/skills/frontend-design/SKILL.md), [Apache-2.0](https://github.com/anthropics/skills/blob/683bc88e56f3e09ba94f7055977f3d3aa499f202/skills/frontend-design/LICENSE.txt).
- **shadcn:** [SKILL.md](https://github.com/shadcn-ui/ui/blob/97ddbf4274ed09d02aa7fd34375f2cf1e48cbbf0/skills/shadcn/SKILL.md), [MIT](https://github.com/shadcn-ui/ui/blob/97ddbf4274ed09d02aa7fd34375f2cf1e48cbbf0/LICENSE.md), [документация навыка](https://ui.shadcn.com/docs/skills).
- **Vercel web-design-guidelines:** [SKILL.md](https://github.com/vercel-labs/agent-skills/blob/063bee94c3f4df8453406c830b0a7df0f2860278/skills/web-design-guidelines/SKILL.md).
- **Vercel react-best-practices:** [SKILL.md](https://github.com/vercel-labs/agent-skills/blob/063bee94c3f4df8453406c830b0a7df0f2860278/skills/react-best-practices/SKILL.md).
- **Vercel composition-patterns:** [SKILL.md](https://github.com/vercel-labs/agent-skills/blob/063bee94c3f4df8453406c830b0a7df0f2860278/skills/composition-patterns/SKILL.md). Общий источник условий этих трёх навыков: [README](https://github.com/vercel-labs/agent-skills/blob/063bee94c3f4df8453406c830b0a7df0f2860278/README.md).
- **Impeccable:** [SKILL.md](https://github.com/pbakaus/impeccable/blob/778c8a7b71ccd5bfe3ca6ac68c15d9d872d0f87d/.agents/skills/impeccable/SKILL.md), [README](https://github.com/pbakaus/impeccable/blob/778c8a7b71ccd5bfe3ca6ac68c15d9d872d0f87d/README.md), [Apache-2.0](https://github.com/pbakaus/impeccable/blob/778c8a7b71ccd5bfe3ca6ac68c15d9d872d0f87d/LICENSE).
- **UI UX Pro Max:** [SKILL.md](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/477bcb28c9812b385cb51a4605ddf30d7b2266e2/.claude/skills/ui-ux-pro-max/SKILL.md), [README](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/477bcb28c9812b385cb51a4605ddf30d7b2266e2/README.md), [MIT](https://github.com/nextlevelbuilder/ui-ux-pro-max-skill/blob/477bcb28c9812b385cb51a4605ddf30d7b2266e2/LICENSE).
- **webapp-testing:** [SKILL.md](https://github.com/anthropics/skills/blob/683bc88e56f3e09ba94f7055977f3d3aa499f202/skills/webapp-testing/SKILL.md), [Apache-2.0](https://github.com/anthropics/skills/blob/683bc88e56f3e09ba94f7055977f3d3aa499f202/skills/webapp-testing/LICENSE.txt).

## Важные различия

**Для таблиц:** shadcn skill помогает собрать UI; TanStack Table реализует логику списка. Навыки Excel/XLSX относятся к файлам таблиц и не заменяют интерфейс клиентской базы. Для нашей CRM сначала интересны поиск, понятные колонки, фильтры и мобильное отображение.

**Для дизайна:** достаточно одного основного навыка и отдельной проверки результата. Несколько конкурирующих визуальных инструкций не гарантируют согласованный дизайн. Критерии нашего проекта: мастер пользуется телефоном, быстро находит адрес, создаёт заявку сообщением и видит следующие действия.

**Для лицензий:** у Anthropic условия отдельных навыков различаются. Apache-2.0 подтверждена здесь для frontend-design и webapp-testing; её нельзя автоматически переносить на весь репозиторий, включая навыки работы с документами.

**Для исполнения:** некоторые материалы содержат скрипты, установщики, hooks или обращения к внешним источникам. Impeccable включает больше, чем Markdown-инструкции; UI UX Pro Max использует Python-ресурсы. Vercel web-design-guidelines загружает актуальные рекомендации по удалённому адресу. При будущем подключении следует проверить состав и закрепить нужную версию; сейчас ничего из этого не выполнялось.

## Актуальные материалы OpenAI

README [openai/skills](https://github.com/openai/skills/blob/49f948faa9258a0c61caceaf225e179651397431/README.md) помечает этот репозиторий устаревшим и направляет к `openai/plugins`. Поэтому старый каталог не принят за актуальный источник новых установок.

В [build-web-apps](https://github.com/openai/plugins/tree/5fd93af4cd0c623e020d0cc7e9ce178b4ac1f70f/plugins/build-web-apps) перечислены навыки frontend-app-builder, frontend-testing-debugging, react-best-practices и shadcn-best-practices. Их можно изучить позднее как официальный набор примеров. Лицензии и условия каждого конкретного пакета отдельно не подтверждены; общий статус «от OpenAI» не заменяет такую проверку.

Первоисточники: [README openai/plugins](https://github.com/openai/plugins/blob/5fd93af4cd0c623e020d0cc7e9ce178b4ac1f70f/README.md), [официальная документация навыков](https://learn.chatgpt.com/docs/skills-and-plugins), [упаковка плагина](https://developers.openai.com/codex/plugins/build).

## Codex и AntiGravity

В актуальной документации AntiGravity навыки проекта располагаются в `.agents/skills/<имя>/`; старое расположение `.agent/skills/` также поддерживается. Это сведения из документации, а не проверка версии приложения на текущем Mac.

Общий формат `SKILL.md` помогает переносить инструкции между агентами. Команды, инструменты, глобальные пути и hooks могут различаться, поэтому поддержка формата не означает полную совместимость любого установщика. Наши идеи и требования остаются в `docs`, а подключение навыков — отдельное будущее действие.

Первоисточники: [AntiGravity Skills](https://antigravity.google/docs/skills), [Agent Skills specification](https://agentskills.io/specification).

## Что можно добавить позже под этот проект

Идея собственного небольшого навыка: правила клиентских карточек и таблиц сантехника — необходимые поля, состояния заявок, мобильные действия, пустые состояния и связь с командами чата. Это позволит нескольким агентам придерживаться одного UX. Сейчас такой навык не создан: сначала нужно согласовать продукт и интерфейс.

Для возвращения к работе: [контекст проекта](../context.md), [индекс исследования](README.md), [снимок источников](source-snapshot.json).
