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
│   ├── js/
│   │   ├── device-state.min.js
│   │   └── s4.min.js
│   ├── AGENT.md
│   ├── index.md
│   ├── REFERENCE-ELEMENTS.md
│   ├── REFERENCE-UTILITIES.md
│   ├── S4.md
│   └── dependency-map.json
├── AGENTS.md
├── favicon.svg
└── index.html
```

## Подробнее

Архитектура, формулы классов, пресеты и API описаны в [s4/S4.md](./s4/S4.md).

Справочники классов и элементов — в [s4/REFERENCE-UTILITIES.md](./s4/REFERENCE-UTILITIES.md) и [s4/REFERENCE-ELEMENTS.md](./s4/REFERENCE-ELEMENTS.md).

Контракт генерации для AI-агента — в [s4/AGENT.md](./s4/AGENT.md), словарь базовых классов — в [s4/index.md](./s4/index.md).

## Работа с AI-агентом

Шаблон рассчитан на генерацию вёрстки AI-агентом. Для этого в папку `s4/` добавлены два файла:

- [s4/AGENT.md](./s4/AGENT.md) — **контракт генерации С4**: формулы классов, правила, few-shot, запреты. Агент читает его перед вёрсткой и строго соблюдает.
- [s4/index.md](./s4/index.md) — **словарь базовых классов** (оглавление всех утилитарных классов без префиксов устройств). Агент сверяется с ним, чтобы не выдумывать несуществующие классы.

Правила для агента собраны в [AGENTS.md](./AGENTS.md) этого репозитория. Перед началом работы агент изучает перечисленные файлы и верстает только классами С4.

## Лицензия

CC BY-NC-SA. Подробнее - в файле [LICENSE](./LICENSE) (включая дополнительные согласия на коммерческое использование для граждан РФ).
