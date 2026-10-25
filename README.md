# HDB dashboard experiments

A D3 visualization prototype for exploring HDB resale trends and flat categories. JavaScript groups resale records by year, month, town, flat type, and flat model, with metric/time controls and several chart experiments.

## Technical skills

**JavaScript · D3.js · HTML/CSS · jQuery · Bootstrap**

The code demonstrates CSV parsing, date/numeric conversion, aggregation, SVG chart construction, and event-driven updates. `P7.ipynb` separately contains Google Cloud CLI/Cloud Storage setup and file-upload exercises; it does not implement image-model training.

## Key files

- [index.html](index.html): dashboard controls and script wiring.
- [js/main.js](js/main.js): CSV ingestion and grouped aggregates.
- [js/change.js](js/change.js): metric/time/category change handlers.
- `js/lineline.js`, `barfile.js`, `typearea.js`, `typepie.js`, and `stackedfile.js`: chart experiments.
- [small.csv](small.csv): sample resale data, stored at the repository root.

## Try the prototype locally

The code requests **`data/small.csv`**, but the checked-in sample is **`small.csv`**. Prepare that expected local path before serving. From the repository root in PowerShell:

```powershell
New-Item -ItemType Directory -Force data
Copy-Item small.csv data/small.csv
python -m http.server 8000
```

Open **http://localhost:8000/**. The HTML loads visualization/UI libraries from CDNs, so internet access is required. No npm build or backend is provided.

## Known gaps

Preparing the CSV path only addresses data loading. Some filter handlers and chart argument/grouping combinations are inconsistent, so complete interactive behavior is not guaranteed. Several chart comments refer to tutorial material; individual ownership is not documented. Additional scripts include alternate experiments. No production deployment, predictive model, or accuracy result is claimed.
