# 🚗 Traffic Flow Analysis using NGSIM Dataset (Lane 4)

## 📌 Project Overview

This project performs **traffic flow analysis** using the NGSIM dataset (Lane 4). It focuses on extracting **macroscopic traffic variables** such as:

* Traffic Density
* Traffic Flow
* Average Speed

The analysis is carried out using **Python (NumPy, Pandas, Matplotlib)** and uses a **virtual detector approach** to compute traffic characteristics over space and time.

---

## 📂 Dataset

The dataset used:

* `Lane4_NGSM.csv`

It contains the following columns:

* `Vehicle_ID`
* `Frame_ID`
* `Local_X` → Lateral position (m)
* `Local_Y` → Longitudinal position (m)
* `v_Vel` → Vehicle speed (m/s)
* `Time` → Timestamp (seconds)

📎 Source file: 

---

## ⚙️ Methodology

### 1. Data Loading & Visualization

* Load dataset using Pandas
* Visualize vehicle trajectories using a scatter plot
* Color represents vehicle speed

### 2. Road & Time Range Extraction

* Compute:

  * Road length range (Y-direction)
  * Time duration of trajectories

### 3. Virtual Detector Setup

* Detectors defined in:

  * **Space:** 40 meters
  * **Time:** 40 seconds
* Grid created using:

  * `np.arange()` for spatial and temporal segmentation

### 4. Detector Table Creation

Each detector stores:

* Spatial range (`Y_start`, `Y_end`)
* Time window (`T_start`, `T_end`)
* Unique `detector_id`

### 5. Vehicle Extraction per Detector

For each detector:

* Filter vehicles inside space-time window
* Compute:

  * Number of vehicles
  * Total distance traveled
  * Total time spent

### 6. Macroscopic Variables Calculation

* **Density (veh/km):**
  $$
  Density = \frac{Total\ Time \times 1000}{Detector\ Length \times Detector\ Time}
  $$

* **Flow (veh/h):**
  $$
  Flow = \frac{Total\ Distance \times 3600}{Detector\ Length \times Detector\ Time}
  $$

* **Speed (km/h):**
  $$
  Speed = \frac{Flow}{Density}
  $$

---

## 📊 Results & Visualizations

The project generates:

### 1. Trajectory Plot

* Vehicle movement in space
* Speed shown using color gradient

### 2. Fundamental Traffic Relationships

* **Speed vs Density**
* **Flow vs Density**
* **Speed vs Flow**

These plots help understand real-world traffic behavior.

---

## 🛠️ Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* tqdm (for progress tracking)

---

## ▶️ How to Run

1. Install dependencies:

```bash
pip install numpy pandas matplotlib tqdm
```

2. Place dataset in the same folder:

```
Lane4_NGSM.csv
```

3. Run the Python script / notebook

---

## 📈 Key Insights

* Traffic flow increases with density up to a point, then decreases (congestion)
* Speed decreases as density increases
* Fundamental diagrams validate traffic flow theory

---

## 🚀 Future Improvements

* Apply machine learning models for prediction
* Extend to multi-lane analysis
* Real-time traffic estimation
* Compare with theoretical models (Greenshields, Greenberg)

---

## 👨‍💻 Author

**Utakarsh Choudhary**


---
