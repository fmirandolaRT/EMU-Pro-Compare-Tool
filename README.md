# EMU Pro Compare Tool

A browser-based calibration comparator and editor for **ECUMaster EMU PRO** `.emupro` files.

**No installation. No server. Open `index.html` in Chrome or Edge and go.**

![EMU Pro Compare Tool](https://img.shields.io/badge/ECUMaster-EMU%20PRO-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Platform](https://img.shields.io/badge/platform-Any%20browser-lightgrey)

---

## Features

- **Side-by-side comparison** of two `.emupro` calibration files
- **Diff highlighting** — differences shown in red, scope panel shows per-scope diff counts
- **Heat-mapped table grid editor** — 2D and 1D calibration tables displayed as coloured grids (blue = low, red = high)
- **Diff view tab** — per-cell A−B difference grid for every table
- **Array editor** — indexed list view with side-by-side comparison column
- **Variable editor** — simple A/B inputs with one-click copy between files
- **Search / filter** parameters by name
- **Diff-only mode** — show only changed parameters
- **Sort** any column
- **Multi-cell copy between files** — select cells in a table (drag / Shift / Ctrl) or rows in an array (click the # column) and copy values A→B or B→A
- **Original file always preserved** — edited files are saved under a new `*_edited.emupro` name; the source calibration is never overwritten
- **Save** modified files back as valid `.emupro` (browser download)
- **Built-in definitions** — parameter names, units, conversions, and axis labels for all firmware versions (0.90 – 2.30) are embedded and load automatically based on file version

---

## Usage

### Online (GitHub Pages)

Open directly in your browser — no install needed:

```
https://fmirandolart.github.io/EMU-Pro-Compare-Tool/
```

### Offline

1. Download `index.html`
2. Open it in any modern browser (Chrome, Edge, Firefox, Safari)
3. Load your files

> The tool is fully self-contained — no internet connection required once the page is loaded. All dependencies are bundled inline.

---

## Loading files

| Method | How |
|--------|-----|
| Click **Open A / Open B** | Opens a file picker |
| **Drag & drop** | Drop an `.emupro` file onto the File A or File B drop zone |

### Definition files (built in)

Definitions for all EMU PRO firmware versions (`project0_090.xml` … `project0_230.xml`)
are embedded in the tool and applied automatically — the right one is picked from the
version of the loaded `.emupro` file (the newer of the two when comparing mixed versions).
This enables human-readable parameter names, units, min/max values, and axis labels
with nothing to download or configure.

To override with a custom definition (e.g. a newer firmware than the tool ships with),
load it via the **Definition XML…** button — a manually loaded definition always takes
priority over the built-in ones.

---

## Editing

| Action | How |
|--------|-----|
| Edit any parameter | **Double-click** a row |
| Navigate cells | Tab / Shift-Tab or arrow keys |
| Save changes | Click **Save** in the dialog (or press Enter for variables) |
| Dismiss without saving | Click **Cancel** or press Escape |
| Save file | **Save A**, **Save B**, or **Save Both** — downloads the modified `.emupro` |

> **Original files are never overwritten.** As soon as a change is applied, the file
> is marked `● edited` in the toolbar and any save downloads it as
> `<name>_edited.emupro`, keeping your original calibration intact.

### Table editor

- Full heat-mapped grid with X/Y axis headers
- Each cell is editable; colours update live as you type
- **Multi-cell selection** — drag to select a block, Shift-click for a range, Ctrl-click to toggle single cells
- **Bulk operations on the selection** — Fill, +/− amount, Scale %, and **A→B / B→A copy** to move values between the two files
- **Diff A−B tab** shows the cell-by-cell difference between the two files

### Array editor

- Indexed list with the other file's values shown alongside for comparison
- Rows with differences are highlighted
- **Row selection** — click the `#` column (Shift: range, Ctrl: toggle), then **A→B / B→A copy** between files

---

## File format

`.emupro` files are ZIP archives containing a single `project.emupro` XML file.
This tool reads and writes that format directly — no conversion needed.

Compatible with **EMU PRO firmware 0.90 – 2.30** (built-in definitions for every released version).

---

## Contributing

Contributions welcome. The entire app is a single `index.html` file — no build step, no dependencies to install.

1. Fork the repo
2. Edit `index.html`
3. Open it in a browser to test
4. Submit a pull request

### Dependencies

| Library | Version | How |
|---------|---------|-----|
| [JSZip](https://stuk.github.io/jszip/) | 3.10.1 | Bundled inline — no CDN required |

The entire app is self-contained in a single `index.html` file with no external dependencies.

---

## License

MIT — see [LICENSE](LICENSE)
