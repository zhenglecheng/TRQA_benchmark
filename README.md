# TRQA_benchmark
Time Series Question Answering Benchmark

<p align="center">
  <img src="figs/data_statistics.jpg" alt="Domain and Task Distribution of TRQA" width="40%">
  <img src="figs/final_conventional.png" alt="Illustration of Conventional Tasks" width="58%">
</p>
<p align="center">
  <img src="figs/final_reasoning.png" alt="Illustration of Advanced Tasks" width="99%">
</p>
<p align="center">
  <b>Figure:</b> Data distribution and tasks of TRQA.
</p>



| **Group**              | **Task**              | **Description**                                             | **Question Type** |
| ---------------------- | --------------------- | ----------------------------------------------------------- | ----------------- |
| **Conventional Tasks** | Anomaly Detection     | Determine whether the input contains anomalies.             | TF                |
|                        | Classification        | Classify the input time series.                             | MC                |
| **Advanced Tasks**     | Characterization      | Determine the characteristics of the time series.           | TF & MC           |
|                        | Comparison            | Compare the characteristics of two time series.             | TF & MC           |
|                        | Data Transformation   | Identify the relationship between raw and transformed data. | TF & MC           |
|                        | Temporal Relationship | Determine the temporal relationship of patches.             | TF & MC & PZ      |




## 🧠 Task Groups in TRQA
TRQA benchmark encompasses two groups of tasks with six diverse tasks designed to evaluate a model's ability of understanding the fundamental properties of time series data. 
The **TRQA** benchmark includes two major groups of tasks designed to evaluate different reasoning abilities in time series analysis.

---

### 🔹 **Conventional Tasks**

These are classic tasks widely explored in traditional time series analysis:

1. **🩸 Anomaly Detection** – Identify irregular or unexpected patterns in a time series.  
2. **🏷️ Classification** – Reason about the relationship between a time series and its underlying conceptual category.

---

### 🔸 **Advanced Tasks**

These novel analytical tasks focus on deeper, intrinsic properties of time series:

3. **📊 Characterization** – Infer fundamental properties such as trend, seasonality, and dispersion.  
4. **⚖️ Comparison** – Reason about relative similarities and differences between two time series.  
5. **🔄 Data Transformation** – Understand relationships between original and transformed time series (e.g., via Fourier transform).  
6. **⏱️ Temporal Relationship** – Capture chronological dependencies among time series patches.

---

> 🧩 **Insight:**  
> These **advanced tasks** push the boundaries of conventional time series modeling—encouraging the development of models that can **grasp cognitive concepts of time series** and **reason over human-posed questions**.


# 📊 Data Collection

In this section, we detail the data sources, including **core datasets**, **anomaly detection datasets**, and **classification datasets**.

---

## 🧩 Core Datasets

We extract data from multiple time-series datasets, including:

**Australian Electricity Demand** — Half-hourly electricity demand for Victoria, Australia (2014).  
**BDG-2 Rat** — Building-level electricity data from the Building Data Genome Project 2.  
**GEF12** — Load forecasting benchmark from the Global Energy Forecasting Competition 2012.  
**ExchangeRate** — Daily exchange rates for currencies of eight countries (1990–2016).  
**FRED-MD** — Monthly macroeconomic indicators from the Federal Reserve Bank.  
**BIDMC32HR** — ICU PPG and ECG recordings from 53 adult patients.  
**PigArtPressure** — Vital sign data from 52 pigs pre/post induced injury.  
**US Births** — Daily number of U.S. births (1969–1988).  
**Sunspot** — Daily sunspot numbers from 1818–2020.  
**Saugeen** — Daily mean river flow data for the Saugeen River (1915–1979).  
**Subseasonal Precipitation** — Daily precipitation (1948–1978).  
**Hierarchical Sales** — SKU-level daily pasta brand sales (2014–2018).  
**M5** — Walmart hierarchical sales forecasting dataset.  
**Pedestrian Counts** — Hourly pedestrian counts from 66 sensors in Melbourne (2009–2020).  
**PEMS03** — Traffic flow data collected by Caltrans PeMS.  
**Uber TLC Daily** — Uber pickup counts in NYC (Jan–Jun 2015).  
**WikiDaily100k** — Daily traffic data for 100,000 Wikipedia pages.

### 📈 Summary of Core Datasets

| **Dataset** | **Total Data Points** | **Domain** |
|--------------|----------------------|-------------|
| AustralianElectricityDemand | 1,153,584 | Energy |
| BDG-2 Rat | 4,728,288 | Energy |
| GEF12 | 788,280 | Energy |
| ExchangeRate | 56,096 | Finance |
| FRED MD | 76,612 | Finance |
| BIDMC32HR | 8,000,000 | Healthcare |
| PigArtPressure | 624,000 | Healthcare |
| USBirths | 7,275 | Healthcare |
| Sunspot | 73,924 | Nature |
| Saugeenday | 23,711 | Nature |
| SubseasonalPrecip | 9,760,426 | Nature |
| HierarchicalSales | 212,164 | Sales |
| M5 | 58,327,370 | Sales |
| PedestrianCounts | 3,130,762 | Transport |
| PEMS03 | 9,382,464 | Transport |
| UberTLCHourly | 1,129,444 | Transport |
| WikiDaily100k | 274,099,872 | Web |

---

## 🚨 Anomaly Detection Datasets

We extract data from multiple anomaly detection benchmarks (e.g., [Paparrizos et al., 2022](#), [Su et al., 2019](#)), including:

- **MGAB** – Mackey–Glass time series exhibiting chaotic behavior and synthetic anomalies.  
- **ECG** – Electrocardiogram recordings with anomalies corresponding to ventricular premature contractions.  
- **Genesis** – Spacecraft telemetry data from a pick-and-place demonstrator.  
- **GHL** – Gasoil Heating Loop data with simulated cyber-attacks.  
- **Occupancy** – Room occupancy monitoring using temperature, humidity, light, and CO₂ data.  
- **SMD** – Server Machine Dataset from a large Internet company, labeled for anomaly detection.

### 🧾 Summary of Anomaly Detection Datasets

| **Name** | **# Samples** | **Domain** |
|-----------|---------------|------------|
| ECG | 17,862 | Healthcare |
| SMD | 58,888 | Cyber-security / IT Operations |
| MGAB | 376 | Mathematical Biology |
| Genesis | 274 | Spacecraft Telemetry |
| GHL | 768 | Industrial Control System |
| Occupancy | 8,178 | Environmental Sensing |

---

## 🧠 Classification Datasets

We extract data from the **UCR Archive** ([Dau et al., 2019](#)) using the following criteria:
- Datasets with **≤4 classes**
- Time series length **≤400** time points

A total of **37 benchmarks** were selected, spanning domains such as robotics, energy, healthcare, synthetic, manufacturing, nature, and transport.

### 🗂️ Summary of Classification Datasets

| **Name** | **# Samples** | **# Classes** | **Domain** |
|-----------|---------------|---------------|-------------|
| SonyAIBORobotSurface1 | 486 | 2 | Robotics |
| SonyAIBORobotSurface2 | 771 | 2 | Robotics |
| FreezerRegularTrain | 2,404 | 2 | Energy |
| FreezerSmallTrain | 2,353 | 2 | Energy |
| ToeSegmentation1 | 210 | 2 | Healthcare |
| ToeSegmentation2 | 129 | 2 | Healthcare |
| TwoPatterns | 3,999 | 4 | Synthetic |
| CBF | 757 | 3 | Synthetic |
| Wafer | 5,744 | 2 | Manufacturing |
| ECG200 | 159 | 2 | Healthcare |
| TwoLeadECG | 923 | 2 | Healthcare |
| ECGFiveDays | 704 | 2 | Healthcare |
| DistalPhalanxOutlineCorrect | 690 | 2 | Healthcare |
| MiddlePhalanxOutlineCorrect | 731 | 2 | Healthcare |
| ProximalPhalanxOutlineCorrect | 688 | 2 | Healthcare |
| DistalPhalanxOutlineAgeGroup | 423 | 3 | Healthcare |
| MiddlePhalanxOutlineAgeGroup | 435 | 3 | Healthcare |
| ProximalPhalanxOutlineAgeGroup | 485 | 3 | Healthcare |
| PhalangesOutlinesCorrect | 2,076 | 2 | Healthcare |
| MoteStrain | 1,012 | 2 | Nature |
| GunPointMaleVersusFemale | 362 | 2 | Healthcare |
| GunPointOldVersusYoung | 356 | 2 | Healthcare |
| GunPointAgeSpan | 368 | 2 | Healthcare |
| GunPoint | 169 | 2 | Healthcare |
| Strawberry | 786 | 2 | Nature |
| ItalyPowerDemand | 890 | 2 | Energy |
| Chinatown | 293 | 2 | Transport |
| BME | 137 | 3 | Synthetic |
| PowerCons | 294 | 2 | Energy |
| DodgersLoopWeekend | 111 | 2 | Transport |
| DodgersLoopGame | 115 | 2 | Transport |
| DiatomSizeReduction | 248 | 4 | Nature |
| SmoothSubspace | 236 | 3 | Synthetic |
| UMD | 148 | 3 | Synthetic |
| Wine | 85 | 2 | Nature |
| Coffee | 48 | 2 | Nature |
| ArrowHead | 175 | 3 | Nature |

---

> 📘 **Note:**  
> All datasets are publicly available from their respective repositories or archives.  
> For reproducibility, preprocessing follows official sources or widely adopted community standards.


---
### 🔸 Data Link: 
https://drive.google.com/file/d/12wBN5ZxYZuN8aQnX3qsbkVTqpyM0aaes/view?usp=sharing
---
