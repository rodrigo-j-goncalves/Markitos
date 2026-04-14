# Markitos Editor &nbsp; v1.0.6

A lightweight desktop Markdown viewer and editor with **collapsible bullet lists**, appearance customization. Built with Python and PyQt6.


![Platform](https://img.shields.io/badge/platform-Linux%20%7C%20macOS%20%7C%20Windows-blue)
![Python](https://img.shields.io/badge/python-3.10%2B-blue)

---

## Features

- Pandoc/Quarto-flavoured Markdown — tables, strikethrough, footnotes, task lists, fenced code blocks
- View / Edit toggle — rendered Markdown preview or raw text editor, switch instantly
- Collapsible lists — any bullet or numbered item with children gets a ▶/▼ toggle; click to collapse/expand; toolbar buttons for collapse all / expand all
- Ctrl+Scroll to zoom font size
- Word wrap
- Settings panel
    - font family
    - font size
    - text/background/heading colours
    - line-number gutter colour with live preview
    - Configurable shortcuts
        - toggle Edit/Preview
        - collapse all
        - expand all
- Find bar (works in both view and edit mode)
- Line numbers (text editor), configurable background colour (or auto-derived from theme)
- Smart editing — auto-pair `[]`/`()`, smart Enter continues list markers, auto-renumbers ordered lists on deletion, Tab/Shift+Tab indent/dedent (4 spaces), full undo/redo (Ctrl+Z / Ctrl+Y), URL-paste onto selected text creates a Markdown link
- Settings and window geometry persisted across sessions (`~/.config/markitos/settings.json`)
- PyQt6 with `QWebEngineView` for the rendered view.
- The WebEngine (Chromium-based) provides full HTML5/CSS3 support
- Markdown parser ([mistune 3](https://github.com/lepture/mistune))
- Custom `HTMLRenderer` 
- Collapsible lists
- Non-printing characters
- Indent guides

---

## Requirements

| Package | Version |
|---------|---------|
| Python | 3.10+ |
| PyQt6 | ≥ 6.4 |
| PyQt6-WebEngine | ≥ 6.4 |
| mistune | ≥ 3.0 |
| platformdirs | ≥ 3.0 |

---

## Running

```bash
# Open with no file (starts in edit mode)
python markitos.py

# Open a specific file
python markitos.py myfile.md
```

---

## Keyboard Shortcuts

| Shortcut | Action |
|----------|--------|
| `Ctrl+O` | Open file |
| `Ctrl+S` | Save |
| `Ctrl+Shift+S` | Save As |
| `Ctrl+Shift+Enter` | Toggle Edit / Preview *(configurable; works on main keyboard and numpad)* |
| `Ctrl+E` | Toggle Edit / Preview (menu) |
| `Ctrl+Scroll` | Zoom font size |
| `Ctrl+Shift+C` | Collapse all list items *(configurable)* |
| `Ctrl+Shift+X` | Expand all list items *(configurable)* |
| `Ctrl+F` | Find |
| `Ctrl+Z` | Undo |
| `Ctrl+Y` | Redo |
| `Ctrl+A` | Select all |

Configurable shortcuts can be changed in **Settings → Keyboard Shortcuts**.

---

## Toolbar

```
Open | Save | ─ | Text | ─ | ⊟ Collapse all | ⊞ Expand all | ─ | Word Wrap |  …space…  | Settings
```

- **Word Wrap** — checkable toggle button; stays in sync with View → Word Wrap menu item
- **Settings** — pushed to the far right by an expanding spacer

---

## Settings panel

All appearance options live in **View → Settings** (or the toolbar Settings button).

| Setting | Description |
|---------|-------------|
| Font family / size | Editor font |
| Text / Background / Heading colour | Palette for both edit and rendered view |
| Line spacing (Markdown view) | CSS `line-height` value (e.g. `1.65`, `2`, `2em`) |
| Paragraph spacing (Markdown view) | CSS margin between paragraphs (e.g. `0.6em`, `1em`, `12px`) |
| Text width (Markdown view) | CSS `max-width` of the text column (e.g. `67%`, `860px`) |
| Word wrap | Toggle line wrapping in the text editor |
| Show line numbers | Toggle gutter with line numbers in text editor |
| Line number background | Custom gutter colour, or "Auto" to derive from text/background blend |
| Symbol opacity | Opacity of `·` `→` `¶` markers in text editor (0–100 %) |
| Indent guide colour / opacity / width | Style of the vertical indent guide lines |

---
