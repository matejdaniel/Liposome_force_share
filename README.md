# Force sharing between the liposome biomembrane and viscous core - an experimental study

This repository contains the dataset and Python analysis script for the study **"Force sharing between the liposome biomembrane and viscous core - an experimental study"**. 🧪

The project investigates the mechanical contributions of the lipid bilayer membrane and the encapsulated viscous core in Giant Unilamellar Vesicles (GUVs). We provide raw Atomic Force Microscopy (AFM) data and a comprehensive Jupyter Notebook detailing the entire data processing pipeline.

## 📊 Dataset Description

The experimental data is organized into two groups corresponding to the two liposome populations studied:
* `Data/ha_0xx.jpk-force`: Force curves from GUVs encapsulating a viscous hyaluronic acid (HA) solution.
* `Data/pbs_0xx.jpk-force`: Force curves from GUVs encapsulating a simple Phosphate-Buffered Saline (PBS) solution, which serve as a model for the membrane's response.

Each `.jpk-force` file in these directories represents a single force-indentation measurement performed on an individual liposome in JPK file format. 

---

## 🐍 Jupyter Notebook: `data_processing.ipynb`

The `data_processing.ipynb` notebook provides a complete walkthrough of the analysis pipeline. It is designed to be a transparent and reproducible guide to our methodology. The key processing steps include:

1.  **Data Loading**: Importing the individual force-indentation curves from the `data/` directory.
2.  **Contact Point Identification**: A novel, model-independent algorithm is used to precisely identify the initial contact point between the AFM probe and the liposome[cite: 74]. This method leverages the statistical change in the cantilever's thermal fluctuations upon contact with the sample surface, avoiding assumptions required by traditional model-fitting approaches.
3.  **Curve Alignment and Averaging**: All curves are aligned by setting their identified contact point as the origin (0,0). The aligned curves for each population (HA-filled and PBS-filled) are then averaged to generate a mean mechanical profile.
4.  **Force Deconvolution**: The core's mechanical contribution is isolated by subtracting the average force response of the PBS-filled liposomes (membrane) from the total response of the HA-filled liposomes at corresponding indentation depths.
5.  **Visualization**: Plotting the raw data, averaged curves, and the final deconvolved force contributions of the membrane and the viscous core.


## 🚀 Getting Started

To explore the data and run the analysis on your local machine, follow these steps:

### Prerequisites

Ensure you have Python 3.10+ and the following libraries installed:
* NumPy (v. 1.26.4)
* Pandas
* Matplotlib
* SciPy
* Jupyter Notebook or JupyterLab

You can install the required packages using `pip`:
```bash
pip install numpy pandas matplotlib scipy notebook
