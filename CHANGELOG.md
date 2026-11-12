# Changelog

All notable changes to Ulamander PDF. Newest first. Author: Miguel Granados.

## 0.2.27 — 2026-11-12
### Added
- **Default app for PDFs:** Settings → Documents → «Use Ulamander PDF to open PDFs…». Android opens the system «Default apps» screen, Windows opens Settings → Default apps, Mac shows the Finder steps. The Windows installer now also registers the app so it appears in Windows' «Default apps» list (it could not be listed before).
### Changed
- **Windows updates:** the downloaded installer now runs silently (no full «new installation» wizard), updates in place, keeps shortcuts and reopens the app. The confirmation says the app will close and reopen by itself. (Not yet tested on a real Windows PC.)

## 0.2.26 — 2026-11-12
### Added
- **Version number on Home (phones):** «Ulamander PDF x.y.z» is shown at the bottom of the Home screen, so you can always see which version is installed.

## 0.2.25 — 2026-11-12
### Fixed
- **Light theme, Tools screen on phones:** the tool cards had a fixed dark background, so in the light theme their titles and descriptions (dark text) were almost invisible. They now follow the theme. Home, Create, File, the viewer and the Edit panel were re-checked in the light theme with screenshots.

## 0.2.24 — 2026-11-12
### Fixed
- **Legibility (accessibility audit):** white text on the bright orange buttons had a contrast of only 2.8:1. Primary buttons, page badges and the active segment now use a slightly deeper orange (about 3.9:1 in dark, 4.5:1 in light) while the brand orange stays for icons and highlights.
- **Light theme, bottom bar:** the labels of inactive tabs (Home, Create, File, Tools…) were too faint; they now follow the theme's muted text colour.
### Verified
- All 29 tools opened one by one on a phone-size screen in both themes: no horizontal overflow and no console errors; desktop tool panel opened without errors.

## 0.2.23 — 2026-11-12
### Fixed
- **«+» / «−» zoom jump:** after tapping the zoom buttons (or pinching) the page flickered back for an instant before settling. The new size, scroll position and end of the temporary preview now happen in the same frame, so there is no jump.
- **Search button turned solid orange:** the active state is now an orange outline with a light tint; opening Search also folds the Edit panel so the search bar is never hidden.
- **Light / dark theme:** several cards, buttons and borders used fixed dark colours and looked wrong in the light theme (for example the «On this device» row, the quick tiles, the bottom bar, the close «×» of panels). They now follow the theme.
- **Green notice stuck on screen:** notices now disappear after 6 seconds (or when tapped).
### Added
- **Edit panel can be folded (phones):** drag the handle down, tap the arrow or the handle, and the panel shrinks to a small pill so you can see and scroll the whole page. The edit mode stays active; × still closes it.
- **Leaving a document with changes:** Save / Discard / Cancel dialog on Mac, Windows and Android (when closing the document and when pressing Back on phones).
- **Create → Images to PDF and Merge PDF:** the lists now show thumbnails, size and order, with move up / move down / remove, and a counter. Several files can be chosen at once (system picker on Android and desktop). WebP and other image formats are converted automatically.

## 0.2.22 — 2026-11-12
### Fixed
- **Zoom (+) crashing or glitching on phones:** at high zoom a single page was drawn on a canvas of about 70 million pixels (roughly 290 MB), which made phones close or freeze the app. The canvas size is now capped (12 M pixels on touch devices, 30 M on desktop); at extreme zoom the page is simply a little less sharp.
- **Page flashing blank / shrinking while it redraws:** the page is now drawn off-screen and swapped in at once, and the previous image is stretched meanwhile, so zooming no longer leaves a blank or smaller page.

## 0.2.21 — 2026-11-12
### Changed
- **Phone layout polish:** when the last tool card of a two-column list is alone (Tools, Create), it now spans the full width instead of leaving an empty half row.

## 0.2.20 — 2026-11-12
### Added
- **Recent files (phone):** swipe a recent file to the right to remove it from the list, or to the left to share it. A normal tap still opens it; vertical scrolling is unaffected. (Android opens the system share sheet.)
### Changed
- **New icon set:** all interface icons now come from Lucide (ISC licence): consistent line weight, rounded ends and sharp at every size from phone to desktop. Notice added to THIRD_PARTY_NOTICES.md.

## 0.2.19 — 2026-11-12
### Fixed
- **Desktop app blocked its own files:** the security policy did not allow the app to read its own bundled files with `fetch`. This stopped the password module (protect / unlock a PDF) from loading and could affect other local resources. The app now allows its own files (still no outside network except the licence server and GitHub).
### Improved
- **Faster start:** the OCR engine, the font embedder and the password module are loaded only when you use them. The main script shrank by about 0.8 MB (2.5 MB → 1.7 MB), so the app opens sooner on phones.

## 0.2.18 — 2026-11-12
### Fixed
- **Zoom buttons (+ / −):** they felt frozen because the whole PDF was redrawn on every tap. Now the page scales instantly and is redrawn once, shortly after your last tap, so tapping several times in a row is smooth.
- **Icons on small screens:** the line icons were drawn too thick (they blurred together when small). They now use a finer stroke that stays sharp from phone to desktop.

## 0.2.17 — 2026-11-12
### Fixed
- **Menu Edit:** «Redact» and «Protect with password» no longer appear twice (a duplicate «Protection» submenu was removed; «Remove metadata» stays as its own entry).
- All 29 tools were opened one by one on phone and tablet sizes with no layout overflow and no errors.

## 0.2.16 — 2026-11-12
### Fixed
- **Pinch zoom:** it was delayed and jumpy because the page was redrawn on every finger movement. Now the page follows your fingers instantly and is redrawn once when you let go, centred on the point you pinched.
- **Zoomed pages:** the left side could not be reached after zooming in (the page was centred and its left edge was cut off). You can now scroll to every edge.
- Pinching on the trackpad or on non-document screens no longer zooms the whole interface.
### Added
- **Send by email:** on Android the system share sheet lets you pick Gmail, Outlook, Hotmail or any other mail app. On Mac and Windows the file is saved where you choose, shown in its folder, and your mail app opens with the subject ready (attach the file; desktop mail cannot be attached automatically).
- «Share / Send by email» button in Export for every format.

## 0.2.15 — 2026-11-11
### Fixed
- **Phones and tablets:** the viewer no longer grows wider than the screen. The tool buttons, the zoom buttons and the page edge were cut off on the right on some phones.
- **Landscape phones:** the left tool rail scrolls instead of being cut off, the zoom buttons sit in a row above the bottom bar, and the header and bottom bar are more compact.
- Checked at 320, 390 and 844×390 (phone portrait and landscape), and 768×1024 and 1180×820 (tablet).

## 0.2.14 — 2026-11-11
### Fixed
- **Update check:** «Check for updates» failed with «Could not check, check your connection» on every platform. GitHub's API rejects the `cache-control` request header in CORS preflight; the header was removed (test added).
- Android update check had the same defect.

## 0.2.13 — 2026-11-11
### Fixed
- PDFs with non-embedded standard fonts or Asian text now render correctly: pdf.js fonts and CMaps ship inside the app.

## 0.2.7 — 2026-11-08
### Added
- **Open Word, Excel and CSV files:** `.docx`, `.xlsx`, `.csv` and `.tsv` open straight from Open / drag and drop and are converted to PDF on your device (nothing is uploaded). Word: text, headings, simple lists and tables. Excel: the values of every sheet (dates stored as serial numbers appear as numbers). Images, styles and exact layout are not reproduced.
- **OCR multi-language (on demand):** Spanish, Italian and English stay bundled offline. Other Tesseract languages can be downloaded once from GitHub release `ocr-langs-v1`, verified with SHA-256, and stored on device. Auto-detect (up to 3 languages), searchable list, preprocess, RTL order and CJK vertical PSM. Documents are never uploaded — only language pack binaries may be fetched.
### Fixed
- The update banner no longer shows the raw release notes (it only says the version is ready and offers Restart).
- Excel dates are shown as dates.
- The duplicated “Open a PDF” buttons on Home and All tools were removed (one call to action in the header).
- **Windows:** F11 toggles full screen.
- Wide tables are split into column groups instead of overflowing the page.
### Notes
- Optional OCR packs require publishing release tag `ocr-langs-v1` (`npm run ocr:langs:fetch` then Miguel publishes). Until then non-bundled languages show as Unavailable. Windows / Android physical / signed macOS not verified in this pass.

## 0.2.6 — 2026-11-08
### Fixed
- **Windows:** the menu bar (File, Edit, View…) is now always visible.
- **Windows:** the window / taskbar icon and the favicon use the current logo (they still showed the old orange-framed tile).
- Activation screen no longer gets cut off on short windows or scaled displays (it scrolls).

## 0.2.5 — 2026-11-08
### Fixed
- **Windows:** the installer and the app now show the Ulamander icon (the `.exe` carried the default Electron icon).
- **Android:** launcher icon replaced with the current logo (adaptive + legacy icons).
### Notes
- Windows is built but not yet tested on a real PC. The Android APK of 0.2.5 still has to be built on a machine with the Android SDK.

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
