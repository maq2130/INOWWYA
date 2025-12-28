
# 🕵️ INOWYA Vx.3.8 (Forensic Location Intelligence)

**INOWYA** is a high-performance, single-file HTML application designed for the forensic analysis of large-scale location datasets (such as Google Takeout). It runs entirely in the browser (client-side) to ensure data privacy while utilizing GPU acceleration to visualize hundreds of thousands of data points instantly.

### 🎯 Core Mission

To transform raw, messy coordinate data into a coherent, interactive timeline of a subject's life, allowing investigators to identify patterns, spot anomalies, and export evidentiary reports.

---

### ⚙️ Technical Architecture

* **Format:** Single-File HTML (Runs offline, no server required).
* **Engine:** Vanilla JavaScript with **Web Workers** for multi-threaded processing.
* **Database:** **Dexie.js** (IndexedDB) for handling massive datasets (100k+ points) without UI lag.
* **Rendering:**
* **Leaflet.js:** For standard map layers and vector overlays.
* **Leaflet.glify (WebGL):** For GPU-accelerated rendering of raw GPS pings.
* **D3.js:** For activity charts and calendar heatmaps.


* **Input:** Google Location History (JSON), ZIP archives, or custom `.inowya` Case Files.

---

### 🚀 Key Features

#### 1. Visualization & Mapping

* **Deep Zoom Layers:** Supports Google Streets, Satellite, Hybrid, Traffic, and Carto Dark/Light modes up to Zoom Level 22.
* **Behavioral Color Coding:** Paths are automatically colored by calculated speed:
* 🔵 **Walking** (<5 km/h)
* 🟢 **Cycling** (5–25 km/h)
* 🟡 **Driving** (25–80 km/h)
* 🔴 **Highway** (>80 km/h)


* **GPU Raw Pings:** A dedicated high-performance layer that renders every single GPS point as a discrete dot, capable of handling millions of points.
* **Transparency Controls:** A specialized slider allows you to fade the trajectory lines to reveal the underlying map, while keeping the raw GPS pings opaque for precision analysis.
* **Accuracy Overlay:** Visualizes the "margin of error" for each point as a red circle, helping distinguish between actual movement and GPS drift.

#### 2. Advanced Playback & Timeline

* **Scrubbing Timeline:** A slider allows for instant manual scrubbing through the dataset with immediate visual feedback on the map.
* **Super Slow Motion:** Playback speeds ranging from **0.001x** (frame-by-frame forensic view) to **500x** (rapid life overview).
* **Day-in-the-Life Replay:** Clicking any day on the yearly calendar heatmap instantly isolates that 24-hour period and begins playback.
* **Smart Skip:** The animation engine automatically fast-forwards through long stationary periods (like sleeping) to save review time.

#### 3. Forensic Intelligence

* **Stop Detection:** Automatically clusters points into "Stops" based on configurable duration (e.g., "Anywhere stayed for > 20 mins").
* **Top Locations:** Generates a ranked list of most-visited places, merging nearby stops into single locations.
* **Anomaly Detection:** Scans the dataset for physical impossibilities, such as "Teleportation" events (speed > 800 km/h) or significant data gaps (> 24 hours).
* **Searchable Index:** A real-time search bar allows filtering of the top locations list by address or name.
* **Proximity Rings:** Toggles 100m, 500m, and 1km rings around specific points to check for geofence violations.

#### 4. Case Management & Reporting

* **Annotation System:** Allows investigators to click any point or stop and attach a persistent text note.
* **Forensic Report:** Generates a printable HTML summary of the investigation, including rank-ordered locations, times, and notes.
* **Evidence Export:**
* **CSV:** Raw tabular data for Excel.
* **GPX / KML / GeoJSON:** Standard GIS formats.
* **Case File (.inowya):** A proprietary ZIP bundle that saves the cleaned track data, address cache, and all user annotations into a single file for sharing or archiving.



---

### 🕹️ User Controls

* **Top Left:** Floating Panel (collapsible) containing Data Source, Filters, Layers, and Analysis tabs.
* **Bottom Center:** Playback controls (Play/Pause, Step Frame, Speed, Timeline Scrub).
* **Keyboard Shortcuts:**
* `Space`: Play/Pause
* `Left/Right Arrows`: Scrub/Step Frame
* `?`: Show Shortcuts Overlay



This version represents a **complete forensic suite** capable of handling professional-grade location investigations.
