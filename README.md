# S4 Template HTML

Минимальный базовый набор для старта адаптивного проекта на HTML с использованием **Системы 4 (С4)** — кодо-центричной среды для построения интерфейсов.

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
s4/
├── css/
│   ├── desktop/
│   │   ├── landscape.css
│   │   ├── portrait.css
│   │   └── config.css
│   ├── mobile/
│   │   ├── landscape.css
│   │   ├── portrait.css
│   │   └── config.css
│   ├── tablet/
│   │   ├── landscape.css
│   │   ├── portrait.css
│   │   └── config.css
│   └── elements.css
├── js/
│   ├── device-state.min.js
│   └── s4.min.js
└── S4.md
```

## Подробнее

Архитектура, формулы классов, пресеты и API описаны в [s4/S4.md](./s4/S4.md).

## Лицензия

CC BY-NC-SA. Подробнее — в [s4/S4.md](./s4/S4.md).
