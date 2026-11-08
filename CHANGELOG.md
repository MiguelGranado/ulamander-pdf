# Changelog

All notable changes to Ulamander PDF. Newest first. Author: Miguel Granados.

## 0.2.4 — 2026-11-08
### Added
- **Automatic updates:** a new version is downloaded in the background and a banner offers “Restart to update”. It never restarts by itself and no longer sends you to GitHub. On macOS (no Apple signature yet) the app verifies the download with SHA-512, replaces itself and reopens; on failure it keeps the previous version.
- Files opened from the system (double click / “Open with”) are queued until the app is ready, including `file://` paths.
- Licence and third-party notices bundled with the app.
### Fixed
- Download links in the README pointed to file names that do not exist; they now go to the latest release.
### Notes
- Versions up to 0.2.3 must install 0.2.4 manually once; from then on updates are automatic.
- Windows and Android were not tested on physical devices; the macOS installer is not signed by Apple (first launch: right-click → Open).

## 0.2.2 — 2026-11-05
### Added
- **macOS universal installer** (Intel + Apple Silicon, macOS 11+): `Ulamander-PDF-macOS-universal.dmg`.
- Compression presets (screen, print, archive); `ulamander-pdf://open` deep link (desktop and Android).
- Foundations for automatic updates (verified downloads); update metadata published with each release.
### Improved
- New vector logo and icons on every platform: solid white / black lettering, document drawn as white paper with dark lines, clean PDF badge.
- Security hardening: path allow-list for file access, strict content-security policy, blocked pop-ups and navigation.
### Notes
- Windows and Android builds were not tested on physical devices yet; macOS tested on Apple Silicon and, emulated, on Intel.

## 0.2.1 — 2026-11-04
### Added
- New logo and app icon for macOS, Windows and Android, including adaptive icons and splash screens, with light and dark variants inside the app.
- In-app notice when a newer version is published on GitHub.
- Windows: file associations (PDF as editor; PNG, JPG, WebP, TXT, MD and HTML as viewer) and right-click entries “Edit with Ulamander PDF” and “Create PDF with Ulamander PDF”.
### Improved
- Light theme: higher contrast for notices, banners, diff view, icons and disabled menu items; the viewer background no longer turns grey.
- Uniform, rounded buttons; narrow windows scroll the navigation instead of overlapping.
- Smoother freehand signature (curve smoothing, coalesced pointer events) and instant tooltips.
### Notes
- The Windows installer is built but has not been verified on a physical PC yet.

## 0.2.0 — 2026-11-01
### Added
- Native menus per platform, Settings, open/save/revert, system print dialog.
- Export to DOCX, PPTX, XLSX, images (choose resolution), TXT, Markdown, HTML and RTF.
- Import to PDF from images, text, HTML, clipboard and scanner.
- Password protection (AES-256), bookmarks, forms, metadata cleaning, read aloud, command palette, advanced search and split view.

## 0.1.0 — 2026-10-29
- First public build: home, all-tools gallery, document view, annotations, signatures, page tools, OCR, editable object layers and activation by personal key.
