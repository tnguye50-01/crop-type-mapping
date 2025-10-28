**Master's thesis — Crop type mapping in Natore District, Bangladesh**

Short, reproducible GEE workflow for mapping crop types from Sentinel-2 time-series using monthly temporal composites and a Random Forest classifier.

---

## Quick overview
- **Goal:** Produce and validate an accurate crop-type map for Natore District using Sentinel-2 and Google Earth Engine (GEE).  
- **Approach:** Build temporal composites (monthly or 15-day), create a temporal band stack, train a Random Forest (RF) model, and evaluate accuracy.

---

## What’s in this repo
- `gee_crop_mapping.js` — Main GEE script: preprocessing → temporal composites → training → classification → accuracy assessment.  
- `thesis_progress_tracker.html` — Simple web task tracker (uses Firebase).  
- `/data/` *(coming soon)* — AOI and ground truth files (GeoJSON / CSV / shapefiles).  
- `/report/` *(coming soon)* — Thesis drafts and final manuscript.

---

## Technologies
GEE (JavaScript), Sentinel-2 (SR), Random Forest classifier, Git / GitHub.

---

## Quick start
1. Open `gee_crop_mapping.js` in the **GEE Code Editor**.  
2. Import or point the script to your AOI and ground truth FeatureCollection (place files in `/data/` or upload to your GEE assets).  
3. Set study period, classes, and parameters at the top of the script.  
4. Run the script to generate composites, train the RF, and produce the classified map.  
5. Use `Export.image.toDrive()` / `Export.table.toDrive()` (configured in the script) to export GeoTIFFs and accuracy tables.

---

## Notes / best practices
- Preserve `system:time_start` in mapped functions (required for correct temporal stacking).  
- Keep train/validation split reproducible (set seeds).  
- Document any secondary ground truth sources if field data are unavailable.


