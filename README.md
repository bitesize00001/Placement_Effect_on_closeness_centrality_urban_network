# Placement_Effect_on_closeness_centrality_urban_network

This repository accompanies the paper:

**"Normalized closeness centrality of urban networks: impact of the location of the catchment area and evaluation based on an idealized network"**  
Hsiao-Hui Chen & Udo Dietrich (2023), *Applied Network Science*  
[DOI: 10.1007/s41109-023-00585-0](https://doi.org/10.1007/s41109-023-00585-0)

##  Project Overview

Urban street network analysis often relies on centrality measures calculated within bounded areas ("catchment areas"). However, where these boundaries are placed can distort results — a challenge known as the **placement effect**. 

This project:
- Quantifies the impact of catchment center placement on **closeness centrality**.
- Proposes a **normalized closeness centrality** metric to adjust for varying node counts.
- Introduces a comparison with an **idealized grid network** to establish a reference.
- Identifies a **threshold distance of 100m**, beyond which placement effects significantly bias centrality measures.

---


## Workflow Summary
### 1. Define 8 Catchment Areas
Around Plaza de los Luceros, Alicante (Spain), with the center shifted from 0m to 1500m.

### 2. Extract Street Networks
Using OpenStreetMap (OSM) with osmnx, filtered for walkable path types.

### 3. Calculate Metrics for a Fixed Node (Red Node)
- Closeness centrality (Cc)
- Normalized closeness centrality (Cn = (N - 1) × Cc)
- Average shortest path distances

### 4. Compare with Idealized Network
A synthetic grid network where nodes are evenly distributed
Benchmark closeness centrality (≈0.871 1/km)

### 5. Visualize Results
Plotting how metrics change as center shifts
Detecting the threshold at which distortion becomes significant
---
## Key Results
- Metric	Observation
- Closeness Centrality (Cc)	Decreases as center moves away from target node
- Normalized Closeness (Cn)	Adjusts for network size; aligns more with spatial logic
- Threshold Distance	If center moves >100m, bias exceeds 2%
- Idealized Benchmark	Cn ≈ 0.871 1/km in grid networks
---
## Figures and Table References
This notebook reproduces:
- Table 1 — Node metrics across 8 catchments
- Figure 4a — Closeness centrality vs. distance
- Figure 4b — Normalized centrality vs. distance (real vs. idealized)
- Figure 5 — Deviation curve and 100m threshold
---
## Tech Stack
- Python 3.9+
- Jupyter Notebook
- osmnx, networkx, pandas, matplotlib
---
## Author
Dr.-Ing. Hsiao-Hui Chen
Urban data scientist | Health informatics | Network analysis

## License
This project is shared under the terms of the paper's Creative Commons Attribution 4.0 License.
Please cite the original article when using this code or methodology.
