# Wind Dashboard

An interactive map that shows both Wind and Solar generators in MISO 
(Midcontinent Independent System Operator) and SPP (Southwest Power Pool) 
markets from the monthly EIA generator inventory file.

## Data Source
EIA Preliminary Monthly Electric Generator Inventory (based on Form EIA-860M 
as a supplement to Form EIA-860), April 2026. Filtered to MISO, SWPP, and SPA 
balancing authorities, Wind (WND) and Solar (SUN) fuel types only, across 
12 key columns.

## What's Included
- `notebook.ipynb` — data pipeline: reads EIA Excel file, filters by balancing 
  authority and fuel type, exports to nodes.json
- `map.html` — interactive Leaflet map with clustering, wind/solar icons, 
  and click popups showing full generator details

## How to Run
1. Create and activate virtual environment:
   python -m venv venv
   venv\Scripts\Activate.ps1
2. Install dependencies:
   pip install pandas openpyxl
3. Place EIA Excel file in data/ folder
4. Run all cells in notebook.ipynb to generate data/nodes.json
5. Start local server:
   python -m http.server 8000
6. Open browser to http://localhost:8000/map.html

## Tech Stack
- Python, pandas — data pipeline
- EIA Form EIA-860M — data source
- JSON — data exchange format
- Leaflet.js — interactive map
- Leaflet.markercluster — marker clustering
- HTML/JavaScript — frontend