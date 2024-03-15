# Predictive Maintenance System for Metro Train

### The aim of this project is to develop a predictive maintenance system for metro trains using sensor data. The goal is to detect and predict potential failures in metro train systems before they occur, enabling proactive maintenance to minimize downtime, enhance safety, and reduce operational costs.

### Dataset Information
The dataset includes analog and digital sensor readings along with GPS information. Here are the sensors included in the dataset:

## Analog Sensors
* TP2: Pressure on the compressor (bar).
* TP3: Pressure generated at the pneumatic panel (bar).
* H1: Valve activation pressure (bar).
* DV_pressure4: Pressure due to pressure drop from air dryers (bar).
* Reservoirs: Pressure inside air tanks (bar).
* Oil_Temperature5: Compressor oil temperature (°C).
* Flowmeter6: Airflow measured on the pneumatic control panel (m3/h).
* Motor_Current7: Motor current indicating compressor status (A).
## Digital Sensors
* COMP: Electrical signal of the air intake valve on the compressor.
* DV_electric: Electrical signal commanding the compressor outlet valve.
* TOWERS: Signal indicating which tower is drying the air.
* MPG: Activates intake valve to start compressor under load.
* LPS: Signal activated when pressure is lower than 7 bars.
* Pressure_switch: Signal activated when pressure is detected.
* Oil_Level: Activated when oil level is below expected values.
* Caudal_impulses: Signal produced by the flowmeter indicating airflow.
## GPS Information
* gpsLong: Longitude position (°).
* gpsLat: Latitude position (°).
* gpsSpeed: Speed (km/h).
* gpsQuality: Signal quality.

### Repository Structure
* dataset: Contains the CSV file with sensor data of the Metro Train.
* artifacts: Includes preprocessing, models, and loss function files.
* notebooks: Jupyter notebooks for data exploration and modeling.
* scripts: Scripts for data preprocessing and model training.
* README.md: Overview of the project and instructions for setup and usage.

### Code Snippets Overview:- 
- Data preprocessing: Cleaning, feature engineering, and visualization.
- Building predictive models: Using TensorFlow and Scikit-learn for anomaly detection and classification.
- Evaluating models: Generating classification reports and accuracy scores.
- Alerting mechanism: Real-time alerts for potential failures based on sensor data.
- Remaining Useful Life (RUL) estimation: Calculating RUL using failure information.

Usage

Clone the repository:
```bash
git clone https://github.com/your_username/predictive-maintenance-metro.git
```
Install dependencies:
```bash
pip install -r requirements.txt
```
Run scripts or notebooks in the scripts and notebooks directories for data preprocessing, model training, and evaluation.

## Code Overview

### Preprocessing
- Data preprocessing steps include type casting, visualization of timestamps across features, dropping irrelevant columns, checking for outliers, missing values, and duplicate records.
- Multicollinearity is addressed by dropping redundant columns.

### Visualization
- Visualizations are provided for air leak and oil leak incidents, showing sensor readings around the time of failures.

### Remaining Useful Life (RUL) Calculation
- RUL is calculated using the provided failure information.
- Plots show the remaining useful life of the engine and alerts for predictive maintenance.

### Failure Prediction
- Anomaly detection models such as KMeans, Isolation Forest, and One-Class SVM are trained and evaluated.
- Classification models like RandomForest are trained using MultiOutputClassifier for failure prediction.
- Autoencoder neural network is implemented for anomaly detection and reconstruction error-based failure prediction.

### Alerting Mechanism
- Predicted failure information and alerts for predictive maintenance are generated based on historic data.
- Real-time alerts for potential failures are displayed using the trained models and reconstruction errors.

## Conclusion
- Autoencoder-based anomaly detection achieved an accuracy of 94.37%.
- The autoencoder successfully predicted air leak with 0.21% of the dataset, oil leak with 3.07%, and No failure with 96.72%.
- Penalizing the autoencoder with regularization helped avoid overfitting and improved generalization.