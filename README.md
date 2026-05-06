
# 🌊 Animated QR Code Generator

A minimal, single-file web app that generates **living, scannable animated QR codes**. Static QR codes are boring—this tool brings them to life with real-time canvas animations while preserving 100% scannability.

<img width="328" height="328" alt="qr-animated" src="https://github.com/user-attachments/assets/4a32ebfa-2c23-4b37-a83c-c602e6e17f29" />

---

## ✨ Features

- **Real-time Animation:** 4 unique animation modes running at 60fps on HTML5 Canvas.
- **Guaranteed Scannability:** Advanced structural protection ensures phone cameras can still read the code perfectly.
- **Customizable Content:** Type any text or URL and watch the QR code update instantly.
- **Animated Exports:** Download the animation as a video or copy it as a self-contained HTML snippet.
- **Zero Build Step:** Everything lives in a single `index.html` file. No frameworks, no npm, no build tools.

---

## 🎬 Animation Modes

| Mode | Description |
| :--- | :--- |
| **Ripple** | A radial wave of light emanating from the center of the code. |
| **Rain** | A vertical, column-by-column cascading highlight (Matrix-style). |
| **Spiral** | A rotating spiral of brightness sweeping through the data modules. |
| **Breathe** | All data modules pulse together with subtle phase offsets based on distance. |

---

## 🔍 How It Stays Scannable

Animating a QR code usually breaks it. This app uses three strict rules to ensure cameras can still decode it:

1. **Level H Error Correction:** Generates the QR code with the highest possible error correction (30% damage tolerance), falling back to Q/M/L only if the text is too long.
2. **Structural Protection:** Finder patterns, timing patterns, alignment patterns, format info, and separators are strictly excluded from animation. They remain static black squares.
3. **High Contrast Limits:** Animated colors never get too bright. The lightest animated teal (`rgb(5,99,89)`) maintains a >7:1 contrast ratio against the white background. Modules only shrink to 78% of their size, never disappearing.

---

## 📤 Export Options

You can export your animated QR code in three formats:

1. **Record .webm:** Records 3 seconds of the live canvas animation at 30fps using the native MediaRecorder API and downloads it as a lightweight video file. *(Note: WebM is used because browsers cannot natively encode animated WebP/AVIF from a canvas stream).*
2. **Copy Animated HTML:** Copies a completely self-contained, minified HTML document (~2KB) to your clipboard. When pasted into an `.html` file and opened, it runs the exact same animated QR code natively—no images or heavy video files required.
3. **Snapshot .png:** Downloads a high-resolution (2x DPI) static image of the QR code at the current frame, perfect for print.

---

## 🛠 Tech Stack

- **UI:** Vanilla HTML/CSS with `Space Grotesk` font.
- **Rendering:** HTML5 Canvas API (`roundRect`, `shadowBlur`, device pixel ratio scaling).
- **Video Export:** Native `MediaRecorder` + `canvas.captureStream()`.
- **Icons:** Font Awesome 6.

---

## 🚀 Getting Started

No installation required.

1. Download or clone this repository:
   ```bash
   git clone https://github.com/PasiKoodaa/Animated-QR-Code-Generator
   ```
2. Open `index.html` in any modern web browser.

---
