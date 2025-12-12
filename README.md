
# INOWYA - Private Location History Visualizer 📍

**INOWYA** (I Know Where You Are) is a powerful, offline-first visualization tool for Google Takeout Location History data. It operates entirely in your browser using a single HTML file—no data is ever uploaded to a server.

  

## 🚀 Key Features

  * **🔒 100% Privacy Focused:** All processing happens client-side via Web Workers. Your location data never leaves your device.
  * **📂 Drag & Drop Import:** Supports raw JSON, ZIP archives (Google Takeout), and custom `.inowya` project files.
  * **🗺️ Interactive Mapping:**
      * Heatmaps with adjustable radius and intensity.
      * Clickable path lines showing speed and activity.
      * Smart "Stop Detection" to identify places you visited.
  * **📊 Deep Analysis:**
      * **Top Locations:** Automatically clusters stops to find your most visited places (with adjustable merge radius).
      * **Activity Breakdown:** Visualizes time spent moving vs. stationary.
      * **Yearly Heatmap:** GitHub-style contribution graph for your travel history.
  * **⏯️ Time Travel Animation:** "Smart Skip" player that fast-forwards through stationary periods to replay your trips.
  * **🌍 Address Enrichment:** Optional reverse-geocoding (via OpenStreetMap) to turn coordinates into readable addresses.

## 🛠️ Installation & Usage

No installation required\! This is a "Zero-Dependency" tool.

1.  **Download:** Get the latest `index.html` from the [Releases](https://www.google.com/search?q=https://github.com/yourusername/inowya/releases) page.
2.  **Run:** Double-click `index.html` to open it in Chrome, Firefox, or Edge.
3.  **Import Data:**
      * Go to [Google Takeout](https://takeout.google.com/).
      * Export "Location History" (JSON format).
      * Drag and drop the `Records.json` or the `zip` file into the INOWYA window.

## 🎛️ Controls

| Feature | Description |
| :--- | :--- |
| **Smart Date Filter** | Select specific date ranges to analyze trips. |
| **Accuracy Slider** | Filter out noisy GPS points (e.g., \> 500m accuracy). |
| **Merge Radius** | Slider (10m - 500m) to group nearby GPS points into single locations. |
| **Speed Chart** | Interactive D3.js graph showing velocity over time. |

## 🏗️ Architecture

  * **Core:** Native HTML5/JS (ES6+).
  * **Mapping:** [Leaflet.js](https://leafletjs.com/) with CartoDB & ESRI tiles.
  * **Clustering:** `Leaflet.markercluster` for efficient data rendering.
  * **Charts:** [D3.js](https://d3js.org/) for analytics.
  * **Processing:** Dedicated **Web Worker** for non-blocking parsing of large datasets (500MB+ JSON files).

## 🤝 Contributing

Contributions are welcome\! Please feel free to submit a Pull Request.

1.  Fork the Project
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4.  Push to the Branch (`git push origin feature/AmazingFeature`)
5.  Open a Pull Request

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.

-----

*Note: This project is not affiliated with Google. "Location History" is a trademark of Google LLC.*
