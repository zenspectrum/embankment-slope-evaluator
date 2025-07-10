# embankment-slope-evaluator (QGIS + Python)
QGIS Python scripts to calculate slope from DEM and classify embankments as Flat, Adequate, or Steep.

This repository contains a set of QGIS-compatible Python scripts for evaluating the safety of highway embankments using slope calculated from a DEM (Digital Elevation Model). The workflow includes extracting elevation along line features (e.g., cross-sections or chainages) and classifying slope into categories such as Flat, Adequate, and Steep based on predefined thresholds.

> Input datasets (DEM) used in this project are not included in this repository. The scripts are generic and can be adapted to any road elevation dataset.

---

## 📌 Features

- Extracts start and end elevation from DEM along line features
- Computes slope using projected DEM (in meters)
- Classifies slope based on user-defined ranges
- Writes output back to the attribute table
- Built to run directly inside QGIS’s Python Console

---

## 🔧 Requirements

- QGIS 3.x or later
- A projected CRS (e.g., UTM) for both DEM and vector layers
- DEM raster file (.tif)
- Polyline shapefile representing slope analysis lines (e.g., cross-sections)

---

## 📁 Scripts

| File                          | Description                                      |
|-------------------------------|--------------------------------------------------|
| slope_calculation.py        | Adds Z_start, Z_end, Length_m, and Slope fields |
| slope_classification.py     | Classifies slope values into categories          |

---

## 📊 Classification Logic

Slope is calculated as a decimal (rise/run), and classified as:

| Slope Value (decimal) | Class     |
|------------------------|-----------|
| < 0.5                | Flat      |
| 0.5 – 0.667          | Adequate  |
| > 0.667              | Steep     |

These thresholds can be adjusted in the script as per project requirements or predefined guidelines.

---

## 🚀 Usage

1. Open QGIS and load your raster DEM and create slope lines vector layer.
2. Open the *Python Console* in QGIS.
3. Paste and run the appropriate script from the scripts/ folder.
4. Ensure your layers are projected in meters (e.g., UTM) before running.
5. The new fields and classification results will appear in the attribute table.

---

## 🚫 Disclaimer

This repository contains *no actual data*. Scripts are provided for methodological transparency and reuse only. You must supply your own DEM and line features.

---


## 📬 Contact

Feel free to open an issue or contact the repository owner if you'd like to contribute improvements or extensions to this workflow.
