<p align="right">
    <a href="README.md">🇷🇺 Русский</a>
</p>

# S4 Template HTML

A minimal baseline for starting an adaptive HTML project with **System 4 (S4)** — a code-centric environment for building interfaces.

## Installation

### Clone the repository:

```bash
git clone https://github.com/s4-design/s4-template-html.git
cd s4-template-html
```

### Open `index.html` directly in a browser or run a local server:
```bash
npx serve
```

No build step or dependencies are required — it is plain HTML/CSS/JS. `npx serve`[^1] is convenient because it correctly resolves paths to included files.

[^1]: Node.js is required.


## Quick start

```html
<html>
    <head>
        <script src="./s4/js/s4.min.js"></script>
        <script>S4()</script>
    </head>
    <body>
        <button>Button</button>
    </body>
</html>
```

## File structure

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

## Details

S4 markup rules are defined by the JSON contract of the `s4/` distribution:

- [s4/AGENTS.md](./s4/AGENTS.md) — agent workflow and S4 integration into a project.
- [s4/contract/patterns.json](./s4/contract/patterns.json) — entry point: UI intent → S4 element.
- [s4/contract/rules.json](./s4/contract/rules.json) — global restrictions `R1..R6` (mandatory) and recommendations `G1..G4`.
- [s4/contract/elements](./s4/contract/elements) — element specifications (created `<e-*>` and modified native tags).
- [s4/contract/validate-s4.mjs](./s4/contract/validate-s4.mjs) — machine validator for markup.

Any `.md` is secondary: in case of a conflict with `contract/*.json`, the JSON is the source of truth.

## Working with an AI agent

The template is designed for markup generation by an AI agent. For this purpose, an autonomous distribution is added to the `s4/` folder:

- [s4/AGENTS.md](./s4/AGENTS.md) — agent instructions: integration, workflow, restrictions.
- [s4/contract/](./s4/contract) — **S4 contract**: JSON element specifications, utility and variable dictionaries, `R1..R6`/`G1..G4` rules, validator. The single authority for markup.

Project agent rules are collected in [AGENTS.md](./AGENTS.md) of this repository. Before starting, the agent studies the listed files and composes markup using S4 classes only, validating every edit:

- Windows: `node s4\contract\validate-s4.mjs <file.html>`
- Linux/macOS: `node s4/contract/validate-s4.mjs <file.html>`

## License

CC BY-NC-SA. See [LICENSE](./LICENSE) for details (including additional consent for commercial use for citizens of the Russian Federation).