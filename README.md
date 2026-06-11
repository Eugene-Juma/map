# Map Explorer Pro

**A fully self-contained, installable PWA for exploring maps, drawing, and measuring – offline-ready and privacy-first.**

[![PWA Ready](https://img.shields.io/badge/PWA-Ready-blue)](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps)  [![Offline Support](https://img.shields.io/badge/Offline-Ready-green)](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Offline_Service_workers)  [![Privacy First](https://img.shields.io/badge/Privacy-First-darkgreen)](#privacy--security)  [![HTML Only](https://img.shields.io/badge/Single%20File-HTML-orange)](#)

**Map Explorer Pro** is a modern, feature‑rich mapping application that runs entirely in your browser. With 16 open‑source base maps, an extensive set of drawing and measurement tools, route planning, and full offline capability, it puts professional GIS functionality into a single HTML file – no build steps, no servers, no trackers.

---

## ✨ Highlights

- **16 free & premium base layers** – OpenStreetMap, Carto (Dark/Light/Voyager), Esri Satellite/Topo/Street/Ocean, Stadia, OpenTopoMap, and more. Add your own API keys for Bing, Thunderforest, or HERE maps.
- **Collapsible sidebar** – Maximise map space. On mobile, the sidebar slides up from the bottom and can be minimised.
- **Full drawing toolkit** – Place markers (with custom labels), draw lines, polygons, rectangles, circles, and even **freehand paths**. Snap‑to‑feature makes precise editing effortless.
- **Intelligent routing & measurement** – Click to measure distances and bearings. Calculate driving routes using OSRM, or fallback to straight‑line distances. Measurement history keeps a log of all your work.
- **Coordinate flexibility** – View and copy coordinates in **Decimal Degrees (DD), Degrees Minutes Seconds (DMS), or Degrees Decimal Minutes (DDM)**. The format can be toggled with one click.
- **Data import/export** – Support for GeoJSON, CSV, and KML. Paste raw GeoJSON directly, or export your drawings for use in other software.
- **Bookmarks & location tools** – Save your favourite views. Find your location with GPS (clear error messages for insecure contexts), jump to coordinates, or search for places worldwide.
- **Print & share** – Generate printer‑friendly map views or share a Google Maps link.
- **Works offline** – A service worker caches the core app and tiles. Installed as a PWA, it behaves like a native app.
- **Privacy‑first** – All data (drawings, bookmarks, settings) stays in your browser’s `localStorage`. No analytics, no tracking, no external data collection.
- **Highly accessible & responsive** – Keyboard shortcuts for all major actions, clear button labels, ARIA attributes, and a fully responsive layout.

---

## 📦 Installation

Because Map Explorer Pro is a single self‑contained HTML file, you can use it immediately:

1. **Open directly** – Save the `.html` file and open it in any modern browser.
2. **Install as PWA** – When prompted (or via the install banner), install it to your device’s home screen for a full‑screen, offline experience.

No server is required (though for HTTPS‑dependent features like GPS, you may want to run a local server or host it securely).

---

## 🚀 Quick Start

| Action | How |
|--------|-----|
| **Search** | Type a place name or `lat,lng` in the search box (or press `S`). |
| **Navigate** | Use the mouse to pan, scroll to zoom, or arrow keys. |
| **Measure** | Press `D` and click points; double‑click to finish. Distance and bearing appear automatically. |
| **Draw** | Choose a tool from the **Draw** tab or press `M` (marker), `P` (polygon), `R` (rectangle), `C` (circle). |
| **Route** | Press `T`, click a start point, then right‑click → “Route To Here”. |
| **Bookmark** | Press `B` or use the right‑click context menu. |
| **Change base map** | Open the **Layers** tab and select any tile layer. |
| **Toggle sidebar** | On mobile, the hamburger button (bottom‑left) or drag the sheet. |

All keyboard shortcuts are listed under the **Map** tab.

---

## 🧪 Version History

### v2.1 – Foundational Release
- 16 base map layers (free + key‑required)
- Basic drawing tools (marker, line, polygon, rect, circle)
- Measurement display, undo, and clear
- Bookmark management
- GeoJSON export / import
- Service worker for offline PWA
- Dark theme

### v3.0 (Pro) – Major Upgrade
Based on user feedback, this version delivers **polished UI/UX, enhanced performance, and new professional tools**.

**Key improvements over v2.1:**

| Area | What changed |
|------|--------------|
| **UI/UX** | Collapsible, mobile‑optimised sidebar; clearly labeled buttons with icons and keyboard hints; coordinate format toggle (DD/DMS/DDM); minimap; toast notifications; improved colour swatches; slimmer, readable typography. |
| **Performance** | Debounced coordinate updates (`requestAnimationFrame`), minimised reflows, and optimised layer switching. |
| **Drawing** | **Freehand drawing** tool with Douglas‑Peucker smoothing; **snap‑to‑feature** for precise alignment; customisable stroke colour via swatches or colour picker. |
| **Route Planning** | OSRM‑based driving routes with fallback to straight‑line distances; dedicated route panel. |
| **Geolocation** | Clear, user‑friendly error messages when on HTTP (e.g., “GPS needs HTTPS”). |
| **Data Handling** | Added CSV and KML export; paste GeoJSON; full backup/restore; secure JSON parsing and HTML escaping to prevent XSS. |
| **Accessibility** | Keyboard shortcuts for all tools (including freehand `H`, route `T`, print `⎙`); ARIA labels; focus management in modals. |
| **Printing** | One‑click print button that captures the current map view. |
| **Security** | Input sanitisation (`htmlEsc`), coordinate validation (`validLatLng`), safe JSON parse, and API keys stored in `localStorage` only (never transmitted). |
| **PWA** | Install banner, improved service worker caching strategy, and better offline fallback for tiles. |

---

## 🔮 Future Roadmap

Map Explorer Pro is under active development. Planned features include:

- **Vector tile support** – Switch to MapLibre or Maplibre GL JS for smoother, highly customisable vector maps.
- **Cloud sync (opt‑in)** – Encrypted, privacy‑preserving sync of bookmarks and drawings across devices (user‑controlled).
- **Dark/Light mode toggle** – Let users switch themes on demand, with system preference detection.
- **Enhanced editing** – Rotate, scale, and duplicate shapes; multi‑select; layer management (reorder, show/hide).
- **Live collaboration** – Share a session link for real‑time collaborative mapping (peer‑to‑peer via WebRTC, no central server).
- **Geocoding improvements** – Reverse geocoding (click to get address), batch geocoding, and support for more providers.
- **Terrain profiles & elevation** – Draw a path and get an elevation profile using public DEM tiles.
- **Custom tile sources** – Let users add their own XYZ/TMS tile URLs.
- **Extended export formats** – Support for GPX, TopoJSON, and shapefiles.
- **Mobile optimisations** – Native‑like gestures (pinch‑to‑draw, hold‑to‑pan), improved touch drawing.
- **Plugin architecture** – Allow external scripts to extend functionality without compromising security.

---

## 🔒 Privacy & Security

- **No tracking, no ads, no data collection.** The app runs entirely in your browser.
- All personal data (drawings, bookmarks, API keys) is stored in `localStorage` and **never sent to any server**.
- API keys for premium tile layers are stored locally and only sent to the respective tile provider when tiles are requested.
- Input sanitisation and coordinate validation prevent XSS attacks.
- The service worker caches resources locally; no data is uploaded during offline use.

---

## 🛠 Technical Overview

Map Explorer Pro is a **single HTML file** with embedded CSS and JavaScript. It relies on:

- [Leaflet](https://leafletjs.com/) for mapping
- [Leaflet.draw](https://github.com/Leaflet/Leaflet.draw) for drawing tools
- [Leaflet Control Geocoder](https://github.com/perliedman/leaflet-control-geocoder) for search
- [OSRM](https://project-osrm.org/) for routing (external, used only when requested)
- A custom **service worker** (in‑line blob) for offline caching

The entire app is designed to be **offline‑first** once the main script and selected tiles are cached. No build tools or frameworks are used – just open the HTML file and it works.

---

## 📄 License

Map Explorer Pro is open‑source software released under the **MIT License**. You are free to use, modify, and distribute it, provided you retain the original copyright notice and license text.