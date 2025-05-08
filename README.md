# fuxa-widget-library

A community-driven collection of **multi-state SVG widgets** for [FUXA](https://github.com/frangoteam/FUXA), the open-source web-based SCADA visualization tool.

This library helps you build visually rich dashboards using categorized, ready-to-use SVG graphics.

---

## Folder Overview

- [`iframes/`](./iframes) – Custom iframe-based widgets.
- [`mining/`](./mining) – Multi-state symbols for mining systems (e.g. conveyors, crushers).
- [`static-symbols/`](./static-symbols) – Static SVG graphics for general use.

---

## How to Install Widgets in FUXA

1. **Download or Clone this Repository**

   ```bash
   git clone https://github.com/carlbomsdata/fuxa-widget-library.git
   ```

2. **Locate the FUXA Widgets Folder**

   This is located at:

   ```
   /server/_widgets/
   ```

3. **Copy Widgets**

   Copy eg the `mining` folder into the FUXA `_widgets` folder.

4. **Use in FUXA**

   - Open the FUXA editor.
   - Add a **MultiState** widget to your drawing.
   - Choose your uploaded SVG file as the symbol.
   - Bind a variable to control the state changes.

All multi-state SVGs in this repository are named and structured to work directly with FUXA's dynamic state system.

---

## Request New Widgets

Want a specific symbol or have an idea?

- [Open an issue](https://github.com/carlbomsdata/fuxa-widget-library/issues) with a description and (if possible) a reference image.
- Or contribute your own SVGs via a pull request.

---
