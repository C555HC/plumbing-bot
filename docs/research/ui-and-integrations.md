# Компоненты, таблицы, календарь и интеграции

Проверено: 8 октября 2026 года. Это каталог кандидатов, а не утверждённый стек или план реализации. Библиотеки не устанавливались и не запускались.

## Интерфейс CRM и таблицы

| Кандидат | Что даёт | Применение у нас | Условия и границы |
| --- | --- | --- | --- |
| shadcn/ui | Исходники компонентов: формы, диалоги, меню, карточки | Компактный интерфейс мастера и клиента | MIT; полноценную CRM и её серверную часть не предоставляет |
| TanStack Table | Логику таблиц: сортировку, фильтры, выбор строк, страницы | Списки клиентов и заявок | MIT; headless-библиотека, внешний вид собираем отдельно |
| TanStack Virtual | Виртуализацию длинных списков | Возможная оптимизация больших баз | MIT; добавлять только при реальной необходимости |
| React Admin | Каркас административного интерфейса, CRUD и работу с data provider | Более быстрый старт кабинета поверх API | MIT для открытой основы; Enterprise-дополнения имеют отдельные условия |
| AG Grid | Готовую функциональную таблицу | Альтернатива для сложных списков и массовых операций | Community — MIT, Enterprise — коммерческая лицензия; функции различаются |

**Предварительный выбор для изучения:** shadcn/ui + TanStack Table. Официальное руководство shadcn показывает их совместное использование. Это хорошо соответствует небольшим спискам с поиском и фильтрами; окончательный выбор зависит от решения по CRM-основе.

Полезные идеи для будущего интерфейса:

- Клиенты: имя, контакт, адрес, последняя услуга, следующий согласованный выезд.
- Заявки: состояние, время, адрес, исполнитель, наличие недостающих данных.
- Быстрые фильтры «Сегодня», «Ждём запчасть», «Нужен повторный выезд», «Подходит срок обслуживания».
- На телефоне проверить карточки и короткие строки; большие таблицы с десятком колонок оставить для широкого экрана.
- Рассылку показывать отдельным действием с получателями и текстом; выделение строк само по себе ничего не отправляет.

Это наши интерфейсные идеи, а не заявленные функции всех перечисленных библиотек.

Первоисточники: [shadcn/ui README](https://github.com/shadcn-ui/ui/blob/97ddbf4274ed09d02aa7fd34375f2cf1e48cbbf0/README.md), [MIT](https://github.com/shadcn-ui/ui/blob/97ddbf4274ed09d02aa7fd34375f2cf1e48cbbf0/LICENSE.md), [официальное руководство по Data Table](https://ui.shadcn.com/docs/components/base/data-table); [TanStack Table](https://github.com/TanStack/table/blob/6aa0d74946b393f4f316085998bb6ec31c2ef593/README.md), [MIT](https://github.com/TanStack/table/blob/6aa0d74946b393f4f316085998bb6ec31c2ef593/LICENSE); [TanStack Virtual](https://github.com/TanStack/virtual/blob/78371e851e90fd74e984deeb0c3fd8098e2cd4f3/README.md), [MIT](https://github.com/TanStack/virtual/blob/78371e851e90fd74e984deeb0c3fd8098e2cd4f3/LICENSE); [React Admin](https://github.com/marmelab/react-admin/blob/47890673cae903b9c5a33898c07a12ea94205b5a/README.md), [MIT](https://github.com/marmelab/react-admin/blob/47890673cae903b9c5a33898c07a12ea94205b5a/LICENSE.md); [AG Grid: Community и Enterprise](https://www.ag-grid.com/javascript-data-grid/community-vs-enterprise/), [лицензии](https://github.com/ag-grid/ag-grid/blob/0e3b7a65a10806799034d61b15cd4da9dc7513ca/LICENSE.txt).

## Даты, календарь и запись

| Кандидат | Роль | Лицензия | Что проверить позже |
| --- | --- | --- | --- |
| DayPicker | Выбор дня или диапазона дат | MIT | Удобство на телефоне, локализацию, совместимость с выбранными компонентами |
| FullCalendar Standard | Отображение календаря выездов | MIT для Standard | Мобильный вид, длительность визита, переносы; resource timeline относится к Premium |
| React Big Calendar | React-календарь как альтернатива | MIT | Удобство на телефоне, локализацию и подходящее представление расписания |

Календарный компонент не решает доступность мастера, дорогу между адресами, конфликты записей и сохранение бронирования. Эти правила относятся к будущему продукту и серверной логике. Для регулярного обслуживания также нужны правила срока конкретной услуги; автоматического «каждые полгода» для всей сантехники не предполагается.

FullCalendar Premium имеет отдельную лицензию: для коммерческого использования нельзя переносить MIT Standard на весь набор. Если понадобится шкала с отдельной строкой для каждого мастера, нужно отдельно оценить Premium или другую реализацию.

DayPicker — выбор даты, а не готовая система бронирования. Текущий README также различает старый пакет `react-day-picker` и новый `@daypicker/react`; версии проверим при выборе стека.

Первоисточники: [DayPicker README](https://github.com/gpbl/react-day-picker/blob/1bfd4f0776d66f2242b6b32a1f084ab94e2702da/README.md), [MIT](https://github.com/gpbl/react-day-picker/blob/1bfd4f0776d66f2242b6b32a1f084ab94e2702da/LICENSE); [FullCalendar README](https://github.com/fullcalendar/fullcalendar/blob/786d1b27673deef84bc550f936f61b4d4a03a7a0/README.md), [условия Standard/Premium](https://fullcalendar.io/license), [timeline](https://fullcalendar.io/docs/timeline-view); [React Big Calendar README](https://github.com/bigcalendar/react-big-calendar/blob/183783ad45c8b845c2f57c46711c1c4c85047843/README.md), [MIT](https://github.com/bigcalendar/react-big-calendar/blob/183783ad45c8b845c2f57c46711c1c4c85047843/LICENSE).

## Telegram и AI

| Кандидат | Для чего | Статус |
| --- | --- | --- |
| Telegram Mini Apps: официальная документация | Требования платформы, запуск мини-апа, данные пользователя | Первоисточник платформы |
| tma.js | Утилиты интеграции мини-апа с Telegram | Сторонний проект Telegram-Mini-Apps, MIT; не официальный SDK Telegram |
| grammY | Разработка Telegram-бота на JavaScript/TypeScript | MIT; вариант при выборе этого языка |
| aiogram | Разработка Telegram-бота на Python | MIT; альтернативный вариант |
| Vercel AI SDK | Инструменты взаимодействия приложения с AI-провайдерами | Apache-2.0 по файлу LICENSE; не готовая CRM |

Эти инструменты закрывают отдельные части, но не дают готовую базу клиентов, очередь напоминаний или сантехническую запись. Язык и AI-провайдер пока не выбраны. Стоимость работы провайдеров и хостинга не определяется лицензией библиотеки.

В мини-апе данные авторизации Telegram проверяются сервером согласно официальной документации. У AI-команды должна быть связь с реальной заявкой и доступным расписанием: сообщение «запиши завтра» само по себе не подтверждает наличие свободного времени.

Первоисточники: [Telegram Mini Apps](https://core.telegram.org/bots/webapps); [tma.js README](https://github.com/Telegram-Mini-Apps/tma.js/blob/534e6f6ddade50d375750cfc19541f3ee899bca7/README.md), [MIT](https://github.com/Telegram-Mini-Apps/tma.js/blob/534e6f6ddade50d375750cfc19541f3ee899bca7/LICENSE); [grammY](https://github.com/grammyjs/grammY/blob/ee0c650ed0908b2478c12b863afd03aac8e07212/README.md), [MIT](https://github.com/grammyjs/grammY/blob/ee0c650ed0908b2478c12b863afd03aac8e07212/LICENSE); [aiogram](https://github.com/aiogram/aiogram/blob/b17c710ca9a05559e2141e1d16338b83dd50a445/README.rst), [MIT](https://github.com/aiogram/aiogram/blob/b17c710ca9a05559e2141e1d16338b83dd50a445/LICENSE); [AI SDK](https://github.com/vercel/ai/blob/5d42987115905ddf1c2167a2bb72c62d7218ed7c/README.md), [Apache-2.0](https://github.com/vercel/ai/blob/5d42987115905ddf1c2167a2bb72c62d7218ed7c/LICENSE).

## Avito: найденный SDK и незакрытые вопросы

Найден [zlexdev/avitoapi](https://github.com/zlexdev/avitoapi): сторонний Python SDK, MIT. Автор описывает асинхронный доступ и генерацию по Avito OpenAPI; в README есть примеры работы с сообщениями через webhook и polling. Это кандидат для будущего изучения, а не подтверждённая интеграция нашего сервиса.

**Из ранее собранных источников:** официальная документация Bitrix24 описывает передачу сообщений Avito в CRM и ответы обратно. Для категории «Услуги» указан расширенный тариф Avito и профессиональный профиль. Это подтверждает сценарий у конкретной готовой интеграции; условия для собственного приложения нужно выяснять отдельно.

Во время исследования официальная страница Avito API не была доступна из текущего окружения. Права приложения, регистрация, доступные методы, лимиты и условия аккаунта остаются непроверенными. README стороннего SDK не заменяет эти сведения. Человек из Avito также не подключается автоматически к Telegram-боту.

Идеи для проверки позднее: входящие обращения в единый список, уведомление мастеру в Telegram, ответ в исходный чат Avito и предложение клиенту отдельно подключить бота для повторного обслуживания.

Первоисточники: [SDK README](https://github.com/zlexdev/avitoapi/blob/cbbe51736a1e5a4cefa68be6ed9307e8a1d47958/README.md), [MIT](https://github.com/zlexdev/avitoapi/blob/cbbe51736a1e5a4cefa68be6ed9307e8a1d47958/LICENSE), [официальная инструкция Bitrix24](https://helpdesk.bitrix24.ru/open/28202720/), [портал Avito API — для последующей проверки](https://developers.avito.ru/).

## Связанные материалы

- [Сравнение CRM](crm-foundations.md).
- [Скиллы, которые могут помочь собрать и проверить интерфейс](agent-skills.md).
- [Проверенные коммиты и лицензии](source-snapshot.json).
