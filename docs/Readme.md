# 🌊 Triton Trace

> **Automated End-to-End Oil Spill Intelligence & Vessel Attribution System**

Triton Trace is an end-to-end maritime intelligence platform developed for **Smart India Hackathon 2026** (Problem Statement ID: **SIH26143**, Theme: **Disaster Management**). The platform automates the detection of offshore oil spills from satellite SAR imagery, calculates probable slick origins using custom hydrodynamic backtracking, correlates AIS vessel tracks, and generates court-ready legal dossiers to hold polluters accountable.

---

## 🔗 Project Links

* **Live Web Application:** [triton-trace.vercel.app](https://triton-trace.vercel.app)
* **Video Demonstration:** [YouTube Presentation](https://youtu.be/W_7jmK9ub54)

---

## 🚀 Key Features

* **Automated SAR Segmentation:** Processes Sentinel-1 SAR imagery using a DeepLabV3+ model to detect oil slicks and eliminate biogenic lookalikes.
* **Uncertainty-Aware Hindtracking:** Custom-built Lagrangian particle tracking model using CMEMS ocean currents and ERA5 wind vectors to run reverse particle simulations.
* **AIS Spatial Attribution:** Correlates nearby vessel telemetry using a KD-Tree spatial search algorithm and ranks suspects using explainable, physics-based scoring (proximity, heading, speed, timing).
* **Forward Drift Forecasting:** Projects future slick trajectories to issue early alerts for high-risk maritime zones and coastal hotspots.
* **Role-Based Access Control (RBAC):** Tailored workspaces for Researchers, Maritime Authorities, and Enterprises.
* **Legal Dossier Export:** Automatically compiles step-by-step evidence into exportable, tamper-proof PDF case files for maritime court prosecution.
* **Commercial Alibi & Insurance Utility:** Allows shipping companies to generate verifiable alibis against false claims and enables insurers to perform P&I risk assessments.

---

## 🛠️ Tech Stack

### Frontend
* **Framework:** React JS (Vite), Tailwind CSS
* **Mapping & GIS:** Mapbox GL JS, Leaflet, Turf.js

### Backend & Services
* **API Engines:** Node.js, Express.js, FastAPI
* **Database & Caching:** PostgreSQL + PostGIS, DuckDB, Redis
* **Authentication:** JWT, Supabase RBAC / Firebase Auth

### AI / ML & Ocean Models
* **Deep Learning Framework:** PyTorch, TorchGeo
* **Segmentation Architecture:** DeepLabV3+ / U-Net
* **Hydrodynamic Drift Engine:** OpenDrift (OpenOil)
* **Spatial Matching:** Spatial KD-Tree Indexing

### Deployment & Cloud
* **Cloud Platform:** AWS (S3, EKS with GPU Node Pools)
* **DevOps:** Docker, GitHub Actions (CI/CD), Vercel, Render

---

## 🏗️ System Architecture

```text
[ Sentinel-1 SAR Data ] ──► [ AI Segmentation (DeepLabV3+) ] ──► [ Oil Slick Polygon ]
                                                                         │
                                                                         ▼
                                                  [ Hydrodynamic Backtrack (OpenDrift) ]
                                                    (CMEMS Ocean + ERA5 Wind Data)
                                                                         │
                                                                         ▼
[ AIS Telemetry ] ──► [ KD-Tree Matching ] ◄────────────────────────────┘
                              │
                              ▼
                  [ Physics-Based Vessel Ranking ]
                              │
                              ▼
        [ Legal Dossier Export (PDF) ]  /  [ Forward Forecast Alert ]
```

---

## 💻 Getting Started Locally

### Prerequisites
* **Node.js** (v18+)
* **Python** (v3.10+)
* **Docker** & **PostgreSQL** with PostGIS enabled

### 1. Clone the Repository
```bash
git clone https://github.com/your-org/triton-trace.git
cd triton-trace
```

### 2. Frontend Setup
```bash
cd client
npm install
npm run dev
```

### 3. Backend Setup
```bash
cd server
pip install -r requirements.txt
uvicorn main:app --reload
```

---

## 👥 Team Details — CheekyPeas

* **Institution:** Birla Institute of Technology, Mesra
* **Problem Statement ID:** SIH26143
* **Team ID:** 138093
* **Team Name:** CheekyPeas
