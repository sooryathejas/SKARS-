# SKARS V2.0.0

<p align="center">
  <img src="screenshots/SKARS_V2_0_0.png" alt="SKARS V2.0.0" width="900">
</p>

A Windows desktop app for working with PDF files — compression, conversion, merging, extraction, rotation, and basic security tools. Everything runs locally. No uploads, no accounts, no cloud.

Built because iLovePDF is useful but I didn't want to feed my files to a website.

---

## Download

Grab the latest release from the [Releases](../../releases) page and extract the zip. You'll get:

```
SKARS-V2.0.0/
├── SKARS-V2.0.0.exe   ← run this
├── app/               ← app files, don't delete
├── runtime/           ← bundled Java runtime, don't delete
└── README.md
```

Java is bundled inside the zip. You don't need to install anything.

---

## Windows will warn you — here's how to get past it

SKARS isn't signed with a paid certificate, so Windows SmartScreen will block it on first launch. It's safe to run — here's what to do:

**SmartScreen popup ("Windows protected your PC"):**

1. Click **More info**
2. Click **Run anyway**

<br>

> If Windows Defender flags it as a threat, click **See details → Allow on device**. This happens because the exe is new and unrecognized, not because it's actually malicious. The source code is fully open on this repo if you want to check it yourself.

---

## What it does

### Compress

Four modes depending on what you're working with:

| Mode | Use it when |
|---|---|
| **Lossless** | The PDF is already clean and you just want it slightly smaller without any quality loss |
| **Balanced** | General use — good middle ground between size and readability |
| **Small Size** | You need to hit an upload or email size limit |
| **Aggressive Scan** | The PDF is a scan or image-heavy — goes hard on recompression, supports color, grayscale, or B&W output |

<p align="center">
  <img src="screenshots/file_compression.png" alt="File picker during compression" width="900">
</p>

<p align="center">
  <img src="screenshots/file_proccessing.png" alt="Compression in progress" width="900">
</p>

---

### Convert to PDF

<p align="center">
  <img src="screenshots/file_conversion.png" alt="Conversion center" width="900">
</p>

Supported input formats:

- Images (JPG, PNG, etc.)
- Text files — plain TXT, Markdown, CSV, logs
- DOCX
- HTML
- Code files (with line numbers)
- PPTX

DOCX conversion tries engines in this order: LibreOffice → Microsoft Word (if installed) → docx4j → built-in fallback. Fidelity depends on which one ends up running, but LibreOffice gives the best results.

---

### PDF tools

- **Merge** — combine multiple PDFs into one
- **Extract pages** — pull out a range of pages into a separate file
- **Rotate** — rotate all pages in a PDF
- **Unlock** — create a decrypted copy when you know the password
- **Protect** — add an open password to a PDF

Note: SKARS only unlocks PDFs when you already know the password. It does not crack or brute-force anything.

---

## Project layout

```
src/main/java/dev/sooryathejas/skars
├── SkarsApp.java
├── service/      ← PDF, conversion, compression, and security logic
├── ui/           ← Swing desktop UI
└── util/         ← Shared file and PDF helpers
```

---

## Privacy

All processing happens on your machine. No file ever leaves your computer. No account needed, no telemetry, no cloud API calls for core features.

---

## Support

If SKARS saves you time, you can support it here:

- [GitHub Sponsors](https://github.com/sponsors/sooryathejas)
- [PayPal](https://www.paypal.com/paypalme/SooryaThejas)

---

Built by [Soorya Thejas](https://github.com/sooryathejas)
