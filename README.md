# Process Monitoring & Fault Detection for a Gas Compression Mini-Station

## Overview

This project demonstrates **fault detection and process monitoring** for a simulated gas compression mini-station using **PCA (T² & SPE)** and **Isolation Forest**. It is designed to showcase the application of **multivariate statistics** and **unsupervised machine learning** in detecting sensor drift, valve sticking, and compressor surge.

The project uses **synthetic multi-sensor data** to simulate normal operation and inject faults, providing a realistic environment for testing monitoring techniques.

---

## Features

* Multi-sensor time series data simulation (pressures, temperatures, flow rates, motor current, vibration, ambient conditions, valve positions, lube oil pressure)
* PCA-based monitoring using **Hotelling’s T²** and **SPE (Squared Prediction Error)**
* Isolation Forest anomaly detection
* Alarm combination logic for robust fault detection
* Performance evaluation including precision, recall, F1 score, and detection latency
* Event-level fault detection analysis

---

## Dataset

* **Training set:** 2000 samples of normal operation
* **Test set:** 1500 samples containing 3 injected fault events

### Fault events

1. **Sensor drift** – samples 400–799
2. **Valve sticking** – samples 900–1049
3. **Compressor surge** – samples 1150–1299

All datasets are **synthetic and reproducible** with a fixed random seed.

---

## Installation

1. Clone the repository:

```bash
git clone https://github.com/Collins-CI/Process-Monitoring-Fault-Detection-for-a-Gas-Compression-Mini-Station.git
cd Process-Monitoring-Fault-Detection-for-a-Gas-Compression-Mini-Station
```

2. Install dependencies (Python 3.9+ recommended):

```bash
pip install -r requirements.txt
```

## Dependencies include:

* pandas
* numpy
* scikit-learn
* matplotlib
* seaborn

---

## Usage

Run the Jupyter Notebook `Anomaly Detection in Industrial Machinery Using PCA and Isolation Forest.ipynb`:

```bash
jupyter notebook
```

Steps in the notebook:

1. Import libraries and generate synthetic datasets
2. Preprocess and scale features
3. Fit PCA and compute T² & SPE statistics
4. Train Isolation Forest and compute anomaly scores
5. Generate individual and combined alarms
6. Evaluate performance (precision, recall, F1, event detection, latency)
7. Visualize T², SPE, and combined alarms

---

## Results

* **Precision:** 0.9467

* **Recall:** 0.7100

* **F1 Score:** 0.8114

* **Event-level detection:** all 3 fault events detected

* **Mean detection latency:** 2 samples

* PCA captured ~62% of variance in the first 6 components

* T² threshold = 16.812, SPE threshold = 12.696

* Isolation Forest AUC = 0.80996

**Conclusion:**
The system successfully detects all injected faults with high precision and low latency, demonstrating effective monitoring using PCA and Isolation Forest.

---

## Project Structure

```
├── ProcessMonitoring_FaultDetection.ipynb   # Main notebook with analysis
├── data/
│   ├── train.csv                            # Synthetic training dataset
│   └── test.csv                             # Synthetic test dataset                       
└── README.md
```

---

## Future Work

* Explore **deep learning approaches** (autoencoders, LSTMs) for temporal dependencies
* Apply **moving-window features** to improve sensitivity
* Add **real-time smoothing/debouncing** for alarms
* Tune PCA components and thresholds for different operational risk levels

---

## License

MIT License © 2025

---

## Author

**[Collins I. Chukwuma](https://www.linkedin.com/in/collins-chukwuma-567845216?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app)**
