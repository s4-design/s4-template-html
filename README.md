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
│   └── S4.md
├── favicon.svg
└── index.html
```

## Подробнее

Архитектура, формулы классов, пресеты и API описаны в [s4/S4.md](./s4/S4.md).

## Лицензия

CC BY-NC-SA. Подробнее - в файле [LICENSE](./LICENSE) (включая дополнительные согласия на коммерческое использование для граждан РФ).
