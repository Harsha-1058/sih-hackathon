# Landslide Runout & Impact Simulator

## What it does
1. Accepts a DEM.
2. Accepts XGBoost high-risk coordinates.
3. Estimates local downslope movement from the DEM gradient.
4. Simulates a simplified runout path.
5. Expands the path into an impact corridor.
6. Optionally intersects the corridor with village and road layers.
7. Exports GeoJSON impact zones and CSV results.

## Run

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
streamlit run app.py
```

## Input requirements

Risk CSV:
```text
latitude,longitude,risk
13.512,75.821,HIGH
13.489,75.803,HIGH
```

The DEM should be GeoTIFF with a CRS. For accurate distance/runout calculations, use a projected CRS whose units are metres (for example the appropriate UTM CRS for the study area).

Village and road layers can be GeoJSON, GeoPackage, or Shapefile ZIP uploads.

## Important limitation
This is a simplified educational model. It estimates a potential downslope corridor; it does not model real landslide rheology, volume, friction, entrainment, barriers, rainfall triggering, or calibrated historical runout.
