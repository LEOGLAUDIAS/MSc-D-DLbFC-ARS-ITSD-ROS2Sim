# MSc Dissertation Project
Deep Learning-Based Failure Classification for Autonomous Robotic Systems Using Industrial Time-Series Data and ROS2 Integration
This project investigates the application of deep learning techniques for failure classification in autonomous robotic systems using industrial time-series sensor data. The study focuses on transforming Remaining Useful Life (RUL) information from the C-MAPSS turbofan engine dataset into operational health states and evaluating the effectiveness of deep learning architectures for predictive maintenance applications.

The project develops and evaluates a CNN-LSTM failure classification model capable of identifying three system conditions:

* Healthy State
* Warning State
* Failure State

The research further explores how such classification outputs can be integrated into a ROS2-based robotic framework to support autonomous maintenance decision-making and intelligent monitoring systems.

The study was conducted using Python, PyTorch, Scikit-Learn, and ROS2 concepts, with experiments performed on the NASA C-MAPSS industrial time-series dataset.

---

# Research Aim

To investigate the effectiveness of deep learning models for failure classification using industrial time-series data and explore their potential integration into autonomous robotic systems through a ROS2-based deployment framework.

---

# Objectives

* Develop a deep learning-based failure classification system using industrial sensor data.
* Convert Remaining Useful Life (RUL) values into discrete operational health states.
* Implement time-series classification using a CNN-LSTM architecture.
* Evaluate model performance using Accuracy, Precision, Recall, F1-Score, and Confusion Matrices.
* Analyse sensor importance and degradation-related features.
* Investigate the suitability of the approach for autonomous robotic maintenance systems.
* Propose a ROS2 integration framework for real-time robotic deployment.

---

# Dataset

### NASA C-MAPSS Turbofan Engine Dataset

The study uses the FD001 subset of the NASA C-MAPSS dataset containing:

* Multiple engine units
* Multivariate sensor measurements
* Operational settings
* Degradation progression information

Health-state labels were generated from Remaining Useful Life (RUL):

| Class | State   | RUL Range     |
| ----- | ------- | ------------- |
| 0     | Healthy | RUL > 60      |
| 1     | Warning | 30 < RUL ≤ 60 |
| 2     | Failure | RUL ≤ 30      |

---

# Methodology

### Data Preprocessing

* Missing value handling
* Feature scaling using MinMaxScaler
* RUL calculation
* Health-state label generation
* Sliding-window sequence generation (30 time steps)

### Deep Learning Architecture

#### CNN-LSTM Model

* Conv1D Layer (64 Filters)
* ReLU Activation
* MaxPooling Layer
* Two-layer LSTM Network
* Dropout Regularisation
* Fully Connected Classification Layer

### Training Configuration

* PyTorch Framework
* Adam Optimizer
* Learning Rate = 0.0005
* CrossEntropy Loss
* Class Weight Balancing
* 25 Training Epochs

---

# Evaluation Metrics

The model was evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix
* Feature Importance Analysis

---

# Results

### CNN-LSTM Performance

| Metric            | Value  |
| ----------------- | ------ |
| Accuracy          | 71.97% |
| Weighted F1 Score | 0.70   |
| Macro F1 Score    | 0.52   |

### Class-Level Performance

| Class   | Precision | Recall | F1-Score |
| ------- | --------- | ------ | -------- |
| Healthy | 0.86      | 0.82   | 0.84     |
| Warning | 0.35      | 0.09   | 0.14     |
| Failure | 0.44      | 0.86   | 0.58     |

Key findings showed strong performance for Healthy and Failure state detection, while Warning-state classification remained the most challenging due to class overlap and gradual degradation behaviour.

---

# ROS2 Integration Concept

The project proposes a ROS2-based deployment framework where:

1. Sensor data is collected from robotic systems.
2. Time-series data is processed by the CNN-LSTM classifier.
3. Health-state predictions are generated.
4. ROS2 nodes publish classification outputs.
5. Autonomous maintenance actions or alerts can be triggered.

This provides a pathway towards intelligent predictive maintenance for autonomous robotic platforms.

---

# Technologies Used

* Python
* PyTorch
* Scikit-Learn
* NumPy
* Pandas
* Matplotlib
* Seaborn
* ROS2 (Conceptual Integration)
* NASA C-MAPSS Dataset

---

# Dissertation Contribution

This work contributes to predictive maintenance research by:

* Reframing Remaining Useful Life data as a multi-class failure classification problem.
* Applying CNN-LSTM architectures to industrial time-series degradation data.
* Investigating failure classification rather than failure prediction.
* Exploring deployment pathways for autonomous robotic systems using ROS2.
* Providing insights into sensor importance and degradation behaviour.

---

**Author:** LEO GLAUDIAS

**Programme:** MSc Artificial Intelligence

**Institution:** Berlin School of Business and Innovation (BSBI)

**Supervisor:** Professor Vincent English

**Year:** 2026
