# screenfox
this is a repo for a firefox extention that lets you screenshot, edit that screenshot and distribute it/

## Project Directory Structure

This project uses [Poetry](https://python-poetry.org/) for Python-based tooling (e.g., automation, testing, or packaging scripts). The main extension is implemented in JavaScript/TypeScript.

```
SnapFox/
├── extension/           # Main browser extension source code (JS/TS)
│   ├── background/
│   ├── content/
│   ├── popup/
│   ├── sidebar/
│   └── assets/
├── tests/               # Python and JS/TS tests
├── scripts/             # Python automation scripts (run with Poetry)
├── docs/                # Documentation (including SRS.md)
├── .gitignore
├── README.md
├── SRS.md
├── pyproject.toml       # Poetry configuration
└── LICENSE
```

- Place all browser extension code in the `extension/` directory.
- Use `scripts/` for Python scripts managed by Poetry.
- Add documentation to `docs/`.
- Tests for both Python and JS/TS can go in `tests/`.
