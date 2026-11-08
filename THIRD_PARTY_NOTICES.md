# Third-party notices — Ulamander PDF

El código y materiales **propios** de Ulamander PDF se distribuyen bajo la
**Ulamander Software License 1.0** (`LICENSE`). Este archivo solo documenta
dependencias de terceros incluidas en la app o en el proceso de build.

Las licencias de cada paquete npm siguen vigentes según su `package.json` /
archivos de licencia en `node_modules/`. Resumen orientativo:

| Componente | Licencia (típica) | Uso en la app |
| --- | --- | --- |
| PDF.js (`pdfjs-dist`) | Apache-2.0 | Vista / texto / búsqueda |
| pdf-lib | MIT | Edición de PDF |
| `@pdf-lib/fontkit` | MIT | Fuentes en PDF |
| Tesseract.js | Apache-2.0 | OCR local |
| `@neslinesli93/qpdf-wasm` | Apache-2.0 | Reescritura / compresión |
| docx | MIT | Export Word (texto/tablas) |
| PptxGenJS | MIT | Export PowerPoint |
| write-excel-file | MIT | Export Excel |
| JSZip | MIT | Empaquetado de exports |
| React / react-dom | MIT | UI |
| framer-motion | MIT | Motion puntual |
| Electron | MIT | Escritorio Mac / Windows |
| electron-updater | MIT | Actualizaciones escritorio |
| Capacitor (+ plugins) | MIT | Android |
| Vite / TypeScript / ESLint (dev) | MIT | Build / herramientas |
| Open Sans · Noto Serif · Roboto Mono | OFL 1.1 / Apache-2.0 | Fuentes incrustadas — detalle en `src/assets/fonts/LICENSES.md` |
| `@noble/curves` | MIT | Firma / verificación de códigos |

Nada de lo anterior convierte el código de Ulamander en software libre ni
mitiga la Ulamander Software License 1.0 sobre el producto.

Para la pantalla in-app «Acerca de → Componentes», ver `src/ui/AboutDialog.tsx`.
