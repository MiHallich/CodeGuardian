# CodeGuardian

**A tiny, private-by-default code review tool that runs entirely in your browser.**

Paste a snippet, choose its language, and get a severity-ranked report with a simple score. No account, API key, backend, or AI service required.

## Features

- **Five languages:** Python, JavaScript, Java, C#, and SQL.
- **Actionable findings:** lightweight rules flag patterns such as dynamic code execution, possible hardcoded secrets, SQL assembled from values, debug output, and unfinished TODOs.
- **Severity levels:** Critical, Warning, and Info help you prioritize what to review.
- **Quick feedback:** a heuristic score, line references, and short explanations make the report easy to scan.
- **Private by design:** analysis happens in the browser. Your source code is not uploaded.
- **No setup required:** open the page directly or serve it locally with Python.

## Get started

### Option 1: Open the page

Download or clone this repository, then open `index.html` in a modern browser.

### Option 2: Run a local web server

Python 3 is only needed to serve the files; the app itself has no runtime dependencies.

```bash
python -m http.server 8000
```

Visit [http://localhost:8000](http://localhost:8000) in your browser.

Choose a language, paste your code, and select **Analyze code**. Use **Load example** to try a sample. You can also press **Ctrl+Enter** (or **⌘+Enter** on macOS) while editing.

## What the score means

The score starts at 100 and subtracts points for each finding:

| Severity | Points deducted |
| --- | ---: |
| Critical | 28 |
| Warning | 12 |
| Info | 4 |

The score bottoms out at 0. It is a small prioritization aid, not a measurement of overall code quality or security.

## Project structure

```text
.
├── index.html   # App layout
├── styles.css   # Responsive interface
├── app.js       # Analysis rules, scoring, and interactions
├── README.md
├── LICENSE
└── .gitignore
```

## How it works

CodeGuardian applies language-specific pattern checks directly to the snippet in your browser. It does not send code to a server, and it does not need credentials or a third-party API.

Pattern matching is intentionally simple. Results can include false positives or miss issues that require parsing, control-flow analysis, or wider project context. Treat the report as a quick first pass, not as a replacement for a compiler, linter, security scanner, or human review.

## Contributing

Ideas and improvements are welcome. For a new rule, include the language, severity, a short explanation, and a small example that should trigger it. Keep checks understandable and avoid presenting heuristic results as guarantees.

## License

This project is released under the MIT License. See [LICENSE](LICENSE).
