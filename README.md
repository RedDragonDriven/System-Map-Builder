# System Map Builder

A single-file browser tool for designing and documenting complex systems as interactive node graphs. Built as a design document companion for large-scale projects — no installation required.
 
---

## Features

- Pannable and zoomable dot-grid canvas for laying out arbitrarily large system maps
- Rounded dark nodes with 8 color presets for category coding
- Curved dependency arrows with arrowheads that seek the nearest node border
- Editable connection labels displayed at arrow midpoints
- Hover tooltips showing each node's description
- Detail panel with full description, logic notes, color picker, dependency list, and dependents list
- Multi-tab system for organizing multiple separate maps in one browser session
- Per-tab undo history (up to 50 steps)
- Zoom to fit, re-center, and reset zoom controls
- Export each map as a `.json` file for saving, sharing, or re-importing
- Export each map as a `.png` image rendered directly on canvas — no external libraries
- Full keyboard shortcut system covering every action

---

## Requirements

No API keys, no server, no installation. All you need is a modern browser (Chrome, Firefox, Edge, or Safari 15.4+).

An internet connection is required on first load to fetch the two display fonts (Rajdhani and Share Tech Mono) from Google Fonts. Once cached by your browser, the tool works offline. The PNG export will fall back to system fonts if the web fonts have not yet loaded.

---

## Usage

1. Open `SystemMapBuilder.html` in any modern browser
2. Click **+ Add Node** or press `N` to create your first node — give it a name, a hover description, and logic notes
3. Click **Connect** or press `C` to enter connect mode, then click a source node followed by a target node to draw a dependency arrow
4. Click any node to open the detail panel — edit its color, add a label to each connection, and view its full dependency and dependents lists
5. Double-click the map title in the top-left of the toolbar to rename the current tab
6. Use **Export .json** or `Shift+E` to save your map, and **Import .json** or `Shift+I` to restore it

---

## Keyboard Shortcuts

| Key | Action |
|---|---|
| `N` | Add node |
| `E` | Edit selected node |
| `Del` / `Bksp` | Delete selected node |
| `C` | Toggle Connect Mode |
| `R` | Re-center view |
| `F` | Zoom to fit all nodes |
| `Z` | Reset zoom to 100% |
| `Shift+Z` | Undo |
| `Shift+Y` | Redo |
| `Shift+E` | Export .json |
| `Shift+P` | Export .png |
| `Shift+I` | Import .json |
| `Shift+T` | New tab |
| `Shift+W` | Close tab (or Clear All if only one tab remains) |
| `Shift+←` / `Shift+→` | Previous / Next tab |
| `F2` | Rename current tab |
| `Shift+Del` | Clear all nodes and connections |
| `Enter` | Confirm (modal) |
| `Esc` | Cancel / Close |

---

## Sharing Maps

The `.json` export contains everything needed to fully restore a map: node names, descriptions, logic notes, positions, colors, connections, and connection labels. Share the file with a collaborator and they can import it directly — no shared account or cloud service required.

The `.png` export renders the full map to a canvas image cropped to the bounding box of all nodes with a 60px margin. It is intended for embedding in documents or sharing as a visual reference and cannot be re-imported.

---

## Known Limitations

### No auto-save
There is no persistent storage. Closing or refreshing the browser tab will lose all unsaved work. Export your map as a `.json` file regularly and keep it somewhere safe.

### Undo and redo history is session-only
Each tab maintains an independent undo and redo history of up to 50 steps. Taking any new action clears the redo stack for that tab, as is standard. History does not survive a page reload — only exported `.json` files can be restored.

### Fixed canvas size
The world canvas is 6000×6000 units. Maps with an extremely large number of widely-spaced nodes could theoretically approach the edges, though this is unlikely in practice. Use **Zoom to Fit** (`F`) to get a full overview at any time.

### PNG font rendering requires an internet connection
The PNG export uses the same Rajdhani display font as the live canvas. If the page was opened without an internet connection and the font has not been cached by your browser, node names in the export will render in the browser's fallback sans-serif font instead.

### Tab state is session-only
Each tab's map, position, zoom level, and undo history exist only for the duration of the browser session. There is no way to reopen a previous session's tabs — only individually exported `.json` files can be restored.

### Shift+T and Shift+W on some systems
On certain operating systems or browser configurations, `Shift+T` and `Shift+W` may be intercepted before reaching the page. If these shortcuts do not work, use the `+` button in the tab bar and the tab's `✕` close button instead.

---

## Suggestions

If you have ideas for features, improvements, or edge cases this tool doesn't handle well, feel free to open an issue. Feedback is welcome.

---

## License

This project is licensed under the [MIT License](https://mit-license.org/). You are free to use, copy, modify, merge, publish, distribute, and sublicense it, provided the original copyright notice is kept intact. See the `LICENSE` file for the full text.

---

Built with the assistance of [Claude](https://claude.ai), an AI assistant by [Anthropic](https://www.anthropic.com).
