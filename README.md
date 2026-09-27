<p align="right">
    <a href="README.en.md">🇬🇧 English</a>
</p>

# S4 Template HTML

Минимальный базовый набор для старта адаптивного проекта на HTML с использованием **Системы 4 (С4)** — кодо-центричной среды для построения интерфейсов.

## Установка

### Клонировать репозиторий:

```bash
git clone https://github.com/s4-design/s4-template-html.git
cd s4-template-html
```

### Открыть `index.html` в браузере напрямую или запусти локальный сервер:
```bash
npx serve
```

Сборка и зависимости не требуются — это чистый HTML/CSS/JS. `npx serve`[^1] удобен тем, что корректно обрабатывает пути к подключаемым файлам.

[^1]: Требуется установленный Node.js


## Быстрый старт

```html
<html>
    <head>
        <script src="./s4/js/s4.min.js"></script>
        <script>S4()</script>
    </head>
    <body>
        <button>Кнопка</button>
    </body>
</html>
```

## Структура файлов

```
s4-template-html/
├── s4/
│   ├── css/
│   │   ├── desktop/
│   │   │   ├── config.css
│   │   │   ├── landscape-utilities.css
│   │   │   └── portrait-utilities.css
│   │   ├── mobile/
│   │   │   ├── config.css
│   │   │   ├── landscape-utilities.css
│   │   │   └── portrait-utilities.css
│   │   ├── tablet/
│   │   │   ├── config.css
│   │   │   ├── landscape-utilities.css
│   │   │   └── portrait-utilities.css
│   │   ├── elements.css
│   │   └── utilities.css
│   ├── contract/
│   │   ├── elements/
│   │   │   ├── created/
│   │   │   └── modified/
│   │   ├── patterns.json
│   │   ├── rules.json
│   │   ├── utilities.json
│   │   ├── variables.json
│   │   └── validate-s4.mjs
│   ├── js/
│   │   ├── device-state.min.js
│   │   └── s4.min.js
│   ├── AGENTS.md
│   └── dependency-map.json
├── AGENTS.md
├── favicon.svg
└── index.html
```

## Подробнее

Правила вёрстки С4 заданы JSON-контрактом дистрибутива `s4/`:

- [s4/AGENTS.md](./s4/AGENTS.md) — алгоритм работы агента и внедрение S4 в проект.
- [s4/contract/patterns.json](./s4/contract/patterns.json) — точка входа: намерение UI → элемент С4.
- [s4/contract/rules.json](./s4/contract/rules.json) — глобальные запреты `R1..R6` (обязательны) и рекомендации `G1..G4`.
- [s4/contract/utilities.json](./s4/contract/utilities.json) — словарь utility-классов (используется валидатором).
- [s4/contract/variables.json](./s4/contract/variables.json) — публичные CSS-переменные.
- [s4/contract/elements](./s4/contract/elements) — спецификации элементов (созданные `<e-*>` и модифицированные нативные теги).
- [s4/contract/validate-s4.mjs](./s4/contract/validate-s4.mjs) — машинный валидатор вёрстки.

Любой `.md` вторичен: при расхождении с `contract/*.json` — истина в JSON.

## Работа с AI-агентом

Шаблон рассчитан на генерацию вёрстки AI-агентом. Для этого в папку `s4/` добавлен автономный дистрибутив:

- [s4/AGENTS.md](./s4/AGENTS.md) — инструкция для агента: внедрение, алгоритм, запреты.
- [s4/contract/](./s4/contract) — **контракт С4**: JSON-спецификации элементов, словари утилит и переменных, правила `R1..R6`/`G1..G4`, валидатор. Единственный авторитет при вёрстке.

Правила для агента проекта собраны в [AGENTS.md](./AGENTS.md) этого репозитория. Перед началом работы агент изучает перечисленные файлы и верстает только классами С4, а каждую правку проверяет валидатором:

- Windows: `node s4\contract\validate-s4.mjs <file.html>`
- Linux/macOS: `node s4/contract/validate-s4.mjs <file.html>`

## Лицензия

CC BY-NC-SA. Подробнее - в файле [LICENSE](./LICENSE) (включая дополнительные согласия на коммерческое использование для граждан РФ).
