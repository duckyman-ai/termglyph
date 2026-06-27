# TermGlyph

<p align="center"><img src="src/main/resources/icons/term-glyph.svg" width="120" alt="TermGlyph"></p>

<p align="center"><b>An alternative terminal for IntelliJ-based IDEs — xterm.js with Unicode 11,<br>so TUI tools like Claude Code render cleanly without overlapping text or broken layouts.</b></p>

<p align="center">Runs on <b>macOS</b> and <b>Windows</b>.</p>

<p align="center"><img src="https://raw.githubusercontent.com/duckyman-ai/termglyph/main/docs/images/screenshot.png" width="720" alt="TermGlyph screenshot"></p>

TermGlyph embeds [xterm.js](https://xtermjs.org/) 6 inside the IDE's JCEF (Chromium Embedded) browser, giving you a **fast, column‑precise terminal** that sits alongside the built‑in one. Its Unicode 11 support means combining characters, wide glyphs, and emoji all get the correct column width — no overlapping text, no broken box‑drawing, no tofu.

> TermGlyph is a *companion* to the IDE's built‑in terminal. Use whichever fits the task.

---

## Why

TUIs like **Claude Code** depend on precise column counting. When a terminal miscounts a character's width, layouts drift: text overlaps, borders break, and the UI becomes hard to read. TermGlyph runs xterm.js with Unicode 11, which gets column widths right for every script — Latin, CJK, Arabic, Thai, emoji — so **any TUI renders the way it was designed to**.

---

## Features

- ✅ **Clean TUI rendering** — Claude Code's input box, borders, and dense output display without overlapping. Works for any terminal UI that depends on accurate column widths.
- 🗂 **Tabs + native split** — Multiple switchable tabs, plus **Split Right / Split Down / Unsplit** in the tab's right‑click menu, exactly like the IDE's own terminal.
- 🔍 **Find** — `Cmd+F` / `Ctrl+F` with match navigation and active‑match highlight.
- 📋 **Copy, paste, clear** — native right‑click context menu.
- 🏷 **Dynamic tab icons & titles** — the tab follows the running process (Claude Code, Git, Docker, Node.js, Gradle, …). The terminal's OSC title sequence is also honoured.
- 🎨 **Follows your IDE editor theme** — background, foreground, cursor, and selection colours come from the editor colour scheme. ANSI 16‑colour palette from *Editor → Color Scheme → Console Colors*. Truecolor (`COLORTERM=truecolor`) is advertised.
- ⚡ **Fast** — WebGL renderer with automatic DOM fallback, output batching, and anti‑freeze repaints.
- 🪟 **Settings** — *Settings → Tools → TermGlyph*: font family, font size, line height, shell, scrollback, cursor style.

---

## Usage

| Action | Shortcut |
|--------|----------|
| New terminal tab | **+** beside the tabs |
| Close tab | **×** on the tab |
| Split right / split down | right‑click the tab → **Split Right / Split Down** |
| Find | **Cmd+F** (macOS) / **Ctrl+F** |
| Copy | **Cmd+C** (macOS) / **Ctrl+Shift+C** |
| Paste | right‑click → **Paste** |
| Clear screen | **Cmd+K** (macOS) / **Ctrl+K** |
| Send SIGINT | **Ctrl+C** |
| New line (multi‑line TUI input) | **Shift+Enter** |
| Settings | gear (⋮) → **Settings…** |

Each terminal opens at the **project folder**.

---

## Limitations

- **Remote Development / JetBrains Gateway / SSH / dev‑containers**: not supported — TermGlyph is **desktop‑only**. Its terminal (xterm.js in JCEF) is a heavyweight component that renders locally and cannot be forwarded over the Remote Development link. Use the IDE's built‑in terminal for remote sessions.

---

## For plugin developers

Built with the [IntelliJ Platform Gradle Plugin 2.x](https://plugins.jetbrains.com/docs/intellij/tools-intellij-platform-gradle-plugin.html) on Gradle 9, Kotlin 2.4, JBR 17 toolchain.

Marketplace payment rules (for reference; this plugin is **free**): [How plugin developers are paid](https://plugins.jetbrains.com/docs/marketplace/getting-paid.html).

---

## Third‑party assets

- **[xterm.js](https://xtermjs.org/)** + addons (fit, unicode11, webgl) — the terminal renderer, MIT‑licensed.

---

## License

[MIT License](LICENSE) — © 2026 Duckyman.

---

*TermGlyph is an independent project and is not affiliated with or endorsed by JetBrains, Anthropic, or the xterm.js project.*
