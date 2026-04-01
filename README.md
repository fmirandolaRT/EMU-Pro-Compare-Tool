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
- **Save** modified files back as valid `.emupro` (browser download)
- **Definition file support** — load `project0_226.xml` for human-readable parameter names, units, and axis labels

---

## Usage

### Online (GitHub Pages)

Open directly in your browser — no install needed:

```
https://<your-username>.github.io/EMU-Pro-Compare-Tool/
```

### Offline

1. Download `index.html`
2. Open it in **Chrome** or **Edge** (Chromium-based browser recommended)
3. Load your files

> Firefox and Safari have limited support for the File System Access API. Saving works via standard browser download on all browsers.

---

## Loading files

| Method | How |
|--------|-----|
| Click **Open A / Open B** | Opens a file picker |
| **Drag & drop** | Drop an `.emupro` file onto the File A or File B drop zone |

### Optional: Definition file

Load `project0_226.xml` (from your ECUMaster install at
`C:\Program Files (x86)\Ecumaster\EMU PRO\Xml\PRO\Project\`) via the **Definition XML…** button.
This enables human-readable parameter names, units, min/max values, and axis labels.
The tool works without it, falling back to raw parameter IDs.

---

## Editing

| Action | How |
|--------|-----|
| Edit any parameter | **Double-click** a row |
| Navigate cells | Tab / Shift-Tab or arrow keys |
| Save changes | Click **Save** in the dialog (or press Enter for variables) |
| Dismiss without saving | Click **Cancel** or press Escape |
| Save file | **Save A**, **Save B**, or **Save Both** — downloads the modified `.emupro` |

### Table editor

- Full heat-mapped grid with X/Y axis headers
- Each cell is editable; colours update live as you type
- **Diff A−B tab** shows the cell-by-cell difference between the two files

### Array editor

- Indexed list with the other file's values shown alongside for comparison
- Rows with differences are highlighted

---

## File format

`.emupro` files are ZIP archives containing a single `project.emupro` XML file.
This tool reads and writes that format directly — no conversion needed.

Compatible with **EMU PRO firmware 226**.

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
| [JSZip](https://stuk.github.io/jszip/) | 3.10.1 | CDN (loaded from cdnjs) |

For fully offline use, download `jszip.min.js` and change the `<script src=...>` tag to point to your local copy.

---

## License

MIT — see [LICENSE](LICENSE)
