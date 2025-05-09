# fuxa-widget-library

This library contains a collection of SVG-based multi-state symbols specifically designed for use in [FUXA](https://github.com/frangoteam/FUXA) industrial HMI/SCADA dashboards — focused on mining and material handling processes.

![ScreenRecording2025-05-08at21 38 00-ezgif com-video-to-gif-converter](https://github.com/user-attachments/assets/bb1bec0a-026e-40fa-a703-fa9469eb1723)

---

## Folder Overview

- [`mining/`](./mining) – Multi-state widgets for mining systems (e.g. conveyors, crushers).
- [`alarm-history/`](./alarm-history) – A interactive Alarm History Widget.
- [`static-symbols/`](./static-symbols) – Static SVG widgets for general use.

---

## Installation

To install these widgets in your FUXA project:

1. Download or clone this repository.
2. Place eg the `mining/` folder inside FUXA’s widget directory (`/server/_widgets/`).
3. Refresh the browser tab running the FUXA editor.
4. Insert the SVG widgets via the FUXA editor under the Widgets pane.
---

## Request New Widgets

Want a specific symbol or have an idea?

- [Open an issue](https://github.com/tobias-carlbom/fuxa-widget-library/issues) with a description and (if possible) a reference image.
- Or contribute your own SVGs via a pull request.

---

## Widget Preview

### [`mining/`](./mining)

All widgets that are located in the `mining/` folder support dynamic state-based color changes.

| Widget | Preview |
|--------|---------|
| cone-crusher | ![](mining/cone-crusher.svg) |
| conveyor-3d-left | ![](mining/conveyor-3d-left.svg) |
| conveyor-3d-right | ![](mining/conveyor-3d-right.svg) |
| conveyor-feeder | ![](mining/conveyor-feeder.svg) |
| conveyor-long | ![](mining/conveyor-long.svg) |
| conveyor-medium | ![](mining/conveyor-medium.svg) |
| conveyor-medium2 | ![](mining/conveyor-medium2.svg) |
| conveyor-short | ![](mining/conveyor-short.svg) |
| feeder-hopper | ![](mining/feeder-hopper.svg) |
| feeder-left | ![](mining/feeder-left.svg) |
| feeder-left2 | ![](mining/feeder-left2.svg) |
| feeder-right | ![](mining/feeder-right.svg) |
| filter | ![](mining/filter.svg) |
| gyratory-crusher | ![](mining/gyratory-crusher.svg) |
| hopper-flat | ![](mining/hopper-flat.svg) |
| hopper-round | ![](mining/hopper-round.svg) |
| motor | ![](mining/motor.svg) |
| screen | ![](mining/screen.svg) |
| screen2 | ![](mining/screen2.svg) |

---

### 🔧 Multi-State Logic and Behavior

Below is shown the most important state variables that you can bind directly in FUXA editor.

#### `_pn_setState` (Number)

Controls the current state of the widget. Used to change fill color based on system condition.

| `_pn_setState` | Color     | Preview | Description            |
|----------------|-----------|---------|------------------------|
| `0`            | `#ffffff` | ⬜️       | Inactive / Neutral     |
| `1`            | `#00ff00` | 🟩       | Running / OK           |
| `2`            | `#ff9500` | 🟧       | Warning                |
| `3`            | `#ff0000` | 🟥       | Blinking Alarm / Fault          |
| `4`            | `#3c3c3c` | ⬛️       | Stopped / Offline      |
| `5`            | `#dcdcdc` | ◻️       | Disconnected / Unknown |

#### `_pn_indicationMode` (Number)

Controls how the visual indication is rendered:

- `0`: Fill only (default)
- `1`: Stroke only
- `2`: Fill + Stroke

---

### [`static-symbols/`](./static-symbols)

These are **non-interactive, static SVG symbols** that can be used as visual decorations or layout elements in your dashboards. They do not respond to `_pn_setState` or any dynamic binding.

| Widget       | Preview                          |
|--------------|----------------------------------|
| stone-left   | ![](static-symbols/stone-left.svg)   |
| stone-pile   | ![](static-symbols/stone-pile.svg)   |
| stone-right  | ![](static-symbols/stone-right.svg)  |

---

### [`alarm-history/`](./alarm-history)

The alarm-history widget displays a historical log of alarm events in a clean, tabular format. It supports filtering by date and time range, data export to CSV, and refreshing live data.

<img width="1306" alt="Skärmavbild 2025-05-09 kl  09 00 57" src="https://github.com/user-attachments/assets/a8a00eb7-2c71-469c-a4d2-de1d8cbef697" />

#### Installation

1. **Place the widget folder**  
   Copy the entire `alarm-history` folder into your FUXA server under:
   ```
   /server/_widgets/
   ```

2. **Add it in FUXA**  
   In the FUXA editor:
   - Add an **iframe** component to your view.
   - Set the `URL` to:
     ```
     http://<your-node-red-ip>:1881/_widgets/alarm-history/alarmhistory.html
     ```

     _Example_:  
     `http://172.31.0.251:1881/_widgets/alarm-history/alarmhistory.html`

3. **Enable Alarm History API**  
   Go to:  
   **Setup → Frontend Scripts**  
   and make sure to **activate** the `$getAlarmsHistory` function.

---
