# Covtype Classification with CapyMOA

This repository contains a classification model developed to analyze and classify the [Covtype dataset](https://capymoa.org/api/modules/capymoa.datasets.Covtype.html) using the CapyMOA framework (version 0.7.0). The primary objective is to perform classification on forest cover types and address concept drift within streaming data.

## Project Overview

This project uses multiple classifiers to perform real-time, streaming classification on the Covtype dataset. The CapyMOA framework supports these streaming processes, allowing for continuous adaptation to evolving data patterns. To handle concept drift and data imbalance, the project uses specialized metrics and dynamic drift detection.

### Authors
- *Ayan Ahmed* - ayan.ahmed@polytechnique.edu
- *Rayyan Ahmed* - rayyan.ahmed@polytechnique.edu

### Lecturer
- Dr. Mariam Barry

### Date
- November 4, 2024

---

## Contents

1. *Dataset Selection and Task*  
   - *Covtype Dataset*: Multi-class classification of forest cover types, with features related to elevation, distance metrics, and soil types.
   - *Goal*: To predict cover type based on the features and analyze model performance under different conditions, including concept drift.

2. *Data Exploration*
   - *Dataset Statistics*: 54 features, 7 classes, and approximately 51,000 instances used for analysis.
   - *Target Class Distribution*: Examines imbalance across classes and variability in distribution over time.
   - *Attribute Analysis*: Visualization of both numerical (e.g., elevation) and categorical (e.g., soil type) attributes to understand spatial variability and trends.

3. *Experimental Setup*
   - *Algorithms Used*: 
      - Hoeffding Tree
      - Adaptive Random Forest
      - Online Bagging
      - Majority Class Baseline
   - *Hyperparameter Optimization*: Performed using random search.
   - *Evaluation Metrics*:
      - κm (Kappa M) and κt (Temporal Kappa) are chosen to handle class imbalance and to assess adaptability to changes over time.

4. *Results and Analysis*
   - *Performance Evaluation*: Comprehensive analysis based on κm, κt, and wall-clock time.
   - *Observations*: Adaptive Random Forest exhibited the highest κt and κm scores, performing best with concept drift. Hoeffding Tree balanced accuracy and computational efficiency, while Majority Class performed poorly in imbalanced scenarios.

5. *Concept Drift Detection*
   - *Drift Detection*: Utilized ADWIN (Adaptive Windowing) for automatic concept drift detection, with multiple drift points identified, particularly in instances with substantial changes.
   - *Adaptive Models*: Adaptive Random Forest and Hoeffding Tree demonstrated resilience to concept drift, while Online Bagging was less consistent.

6. *Neural Network-Based Analysis*
   - *Architecture*: A custom neural network implemented with PyTorch, leveraging CapyMOA’s instance-based streaming for further classification experiments.
   - *Training Strategy*: Real-time training with a streaming loop and prequential evaluation for continuous assessment of model performance.
   - *Results*: Demonstrated the potential of neural networks for handling non-stationary data with κm values peaking above 90, indicating robust performance over time.

---

## Installation and Setup

1. *Requirements*:
   - Python >= 3.8
   - CapyMOA (version 0.7.0)
   - PyTorch
   

2. *Usage*:
   - To run the classification pipeline with CapyMOA:
     bash
     python main.py
     
   - To visualize concept drift and other metrics:
     bash
     python visualize_metrics.py
     

## Acknowledgments

This project is based on the Covtype dataset and leverages the CapyMOA framework for streaming data analysis.
---
