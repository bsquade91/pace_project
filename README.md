# Commercial PACE Feasibility Underwriting Model

An automated geospatial underwriting engine designed to identify cash-flow positive commercial properties prime for Property Assessed Clean Energy (PACE) financing. Built specifically for the City of St. Louis, MO.

## 📌 Project Overview
While green infrastructure offers massive civic benefits like Urban Heat Island (UHI) mitigation and stormwater retention, adoption requires sound private economics. 

This model bridges the gap between civic sustainability goals and commercial real estate finance. It ingests raw municipal shapefiles and tax records, corrects for missing floor-count data, and applies a strict two-pronged financial viability test:
1. **Legal Constraints:** Project costs must remain under the 20% Loan-to-Value (LTV) PACE financing cap.
2. **Financial ROI:** Projects must generate enough energy savings to fully amortize the installation cost within a standard 20-year PACE financing term.

## ⚙️ Key Technical Features
* **Bifurcated Infrastructure Logic:** Dynamically cross-references building square footage against parcel boundaries.
* **Economies of Scale Math:** Applies fixed mobilization costs vs. variable per-square-foot costs to accurately calculate ROI windows for different sized properties.
* **Data Sanitization:** Utilizes Geospatial "Sanity Caps" to prevent lazy municipal floor-count data from crashing the financial math.
* **Interactive Outputs:** Generates a dynamic, interactive `folium` heatmap overlaid with tier-categorized property boundaries and custom ROI popups. Outputs a prioritized `.csv` targeted for business development teams.

## 🛠️ Tech Stack
* **Python:** Core analytical engine.
* **GeoPandas & Pandas:** Spatial joins, data cleaning, and vectorized ROI calculations.
* **Folium:** Interactive map generation and GeoJSON rendering.
* **NumPy:** Conditional matrix logic.

## 📂 Data Sources
* [City of St. Louis Open Data Portal](https://www.stlouis-mo.gov/data/)
  * Current Parcels Shapefile (`.shp`)
  * Parcel Land & Tax Records (`.dbf`)
