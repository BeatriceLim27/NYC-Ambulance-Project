# 🚑 NYC Ambulance Dispatch Optimisation Project

- The **NYC Ambulance Project** is a full-stack data science solution to enhance **FDNY’s ambulance response performance** across all five NYC boroughs.
- The system integrates **geospatial analytics**, **search optimisation** and **machine learning** to simulate, visualise and recommend data-driven decisions for faster emergency responses.

---

### 🎯 Objectives

- 🗺️ Map ambulance stations and optimise new facility placements.
- 🚦 Simulate and reduce average ambulance response time per borough.
- 🤖 Predict whether a motor vehicle collision is **dangerous** or **safe** using ML.
- 📊 Visualise spatial and temporal collision patterns with weather overlay.

---

### 📂 What's Inside

#### 🔍 Optimisation & Mapping
- `existing_ambulance_stations.ipynb`: Base map of all existing NYC EMS stations using Folium
- `*_map_code.ipynb`: Hill-Climbing + Haversine optimisation for **best new facility site** (per borough) 
  - `Manhattan_map_code.ipynb`, `Queens_map_code.ipynb`, `Bronx_map_code.ipynb`, `Brooklyn_map_code.ipynb`, `Staten_Island_map_code.ipynb`.
- `new_ambulance_stations.html`: Interactive Leaflet visualisation of FDNY EMS station coverage & bottlenecks

#### 🤖 Machine Learning Pipeline
- `merged_weather_collisions.csv`: Engineered weather + collision features for ML model input
- `ML_model.ipynb`: Full ML classification pipeline to predict **dangerous** vs **non-dangerous** crashes

#### 🧠 ML Model Details

- **Target**: `dangerous = 1` if people injured or killed > 0, else 0
- **Features**:
  - Weather (precipitation type, temperature, wind, visibility)
  - Collision type, contributing factor, borough, hour of day, day of week
- **Model**: Random Forest Classifier (with `class_weight='balanced'`)
- **Tuning**: GridSearchCV optimising for **recall**
- **Outcome**: Predicts and flags high-risk collisions for response prioritisation
