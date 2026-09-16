# Local Font Loader

Load local fonts (TTF / OTF / WOFF / WOFF2) in [Obsidian](https://obsidian.md) with Base64
caching. Manage UI, body text, code and LaTeX math fonts separately, with cross-device presets.

Everything stays local — no CDN, no system fonts.

## This repository is build output only

It holds the three files Obsidian loads — `main.js`, `manifest.json` and `styles.css` — exactly
as they are released. There is no build tooling and no source here, which is deliberate: it keeps
what users install and what reviewers read identical to what was published.

**Source code, issue tracker and development documentation live in the source repository:**
<https://github.com/lmce72/obsidian-local-font-loader>

## Installation

**From Obsidian:** Settings → Community plugins → Browse → search for "Local Font Loader".

**Manually:** download `main.js`, `manifest.json` and `styles.css` from the
[latest release](https://github.com/lmce72/obsidian-local-font-loader-release/releases/latest) and
place them in:

```
<your vault>/.obsidian/plugins/obsidian-local-font-loader/
```

Then enable the plugin under Settings → Community plugins.

## Usage

1. Put your fonts in a folder, one subfolder per family:

   ```
   Local-Fonts/
   ├── MyFont/
   │   ├── MyFont-Regular.ttf
   │   ├── MyFont-Bold.ttf
   │   ├── MyFont-Italic.ttf
   │   └── MyFont-BoldItalic.ttf
   └── AnotherFont/
       └── AnotherFont-Regular.otf
   ```

2. Open Settings → Local Font Loader and point the font source directory at that folder.
3. Click **Rescan Fonts**, then **Convert All Fonts** to build the Base64 cache.
4. Assign a family to each category (UI, Text, Heading, Code, Math) and click **Apply Fonts**.

### A note on math fonts

LaTeX rendering is laid out by MathJax from its own pre-built metrics, so a math font only aligns
properly when its glyph metrics match. The settings tab checks this and warns when they do not —
inline code and radicals are the usual casualties. A font built on Computer Modern metrics (such
as Latin Modern Math) matches by construction.

## Requirements

- Obsidian 1.13.0 or later
- Font files in TTF, OTF, WOFF or WOFF2 format

## License

[MIT](LICENSE)
