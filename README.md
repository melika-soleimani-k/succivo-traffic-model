# succivo-traffic-model
# Macroscopic Traffic Modeling & PrT Assignment — Succivo (Naples Metro)

![PTV Visum 2024](https://img.shields.io/badge/PTV_Visum-2024.01-blue)
![OpenStreetMap](https://img.shields.io/badge/Data-OpenStreetMap-green)
![ISTAT](https://img.shields.io/badge/Demographics-ISTAT_2011-orange)
![TomTom](https://img.shields.io/badge/FCD-TomTom_Move_Portal-red)

## Executive Summary
This project develops a macroscopic urban transport model for the municipality of **Succivo** and its surrounding urban corridor in the Naples Metropolitan Area (Campania, Italy). Built using **PTV Visum 2024**, the model integrates **OpenStreetMap (OSM)** spatial geometries, **ISTAT 2011 census tract demographics**, and **TomTom Move Portal Floating Car Data (FCD)** to execute Private Transport (**PrT**) traffic assignments and evaluate arterial congestion bottlenecks.

Developed as part of the *Intelligent Transportation Systems (ITS)* course at **Università degli Studi di Napoli Federico II**.

---

## Network Output & PrT Assignment

![Succivo PrT Traffic Assignment Map](succivo.jpg)

### Observed Bandwidth Volumes (`[veh/h]`):
* **Green Links ($\le 31$ veh/h):** Local access roads and low-density connectors.
* **Yellow Links ($\le 247$ veh/h):** Collector roads and minor arterials.
* **Orange Links ($\le 444$ veh/h):** Sub-arterials with heavy peak demand.
* **Red Links ($> 444$ veh/h):** Major capacity bottlenecks across central Succivo and key external regional connections.

---

## Methodology & Workflow

### 1. Spatial Network & TAZ Construction
* Extracted street geometry and highway networks from **OpenStreetMap (OSM)**.
* Defined Traffic Analysis Zones (TAZs) using **ISTAT 2011 census tract boundaries (SEZ2011)** for Succivo, Sant'Arpino, Orta di Atella, Frattaminore, Cesa, and regional rail connection hubs (*Sant'Antimo-Arpino*, *Gricignano-Teverola*).

### 2. Socio-Economic Trip Generation & OD Matrices
* Calibrated zonal trip production ($P_i$) and attraction ($A_j$) using census variables:
  * **Population (`POP`)**: Residential trip generation.
  * **Employment (`ADDETTI`)**: Worksite trip attraction.
* Formulated time-dependent Origin-Destination (OD) demand matrices across daily time windows:
  * **Morning Peak Hour:** `08:00 – 09:00`
  * **Inter-urban Off-Peak:** `11:00 – 12:00`
  * **Daily Total Window:** `08:00 – 19:00`

### 3. Traffic Assignment & FCD Calibration
* Executed **Private Transport (PrT)** equilibrium traffic assignments in PTV Visum to model route choice and capacity restraint functions.
* Cross-referenced corridor speed profiles using **TomTom Move Portal Floating Car Data (FCD)** to evaluate congestion points along main thoroughfares.

---

## Technical Specifications & Tools
* **Software:** PTV Visum 2024.01-04
* **Spatial Data:** OpenStreetMap (OSM)
* **Census Data:** ISTAT SEZ2011 Census Tracts
* **FCD / Traffic Analytics:** TomTom Move Portal
* **Study Area:** Succivo, Campania, Italy ($40.966^{\circ}\text{N}, 14.253^{\circ}\text{E}$)

---

## Repository Files
* `succivo.jpg`: High-resolution PrT traffic assignment map and bandwidth visualization.
* `succivo_model.ver`: Complete PTV Visum network binary file.
* `README.md`: Technical summary and project documentation.
