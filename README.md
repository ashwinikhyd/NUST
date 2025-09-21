

# Analysis of Unevenly Sampled Data with the Non-Uniform S-Transform (NUST)
This repository contains the Python code and Jupyter notebooks used to develop, test, and validate the Non-Uniform S-Transform (NUST), a time-frequency analysis method for unevenly sampled data. The work here formed the basis of a submission to the ICASSP-2026 conference.

## What's the Problem?
In many real-world fields like astronomy, seismology, or biomedical engineering, we can't always collect data at perfect, regular intervals. This creates unevenly sampled time series, which can be a big problem for traditional signal processing tools like the Fourier Transform. These tools often require interpolation (guessing the missing data), which can create errors, or they use methods that don't make full use of the information we have.

## What is NUST?
The Non-Uniform S-Transform (NUST) is a method designed to solve this problem. It creates a time-frequency map (a spectrogram) that shows you what frequencies are present in your signal and when they appear, working directly on the unevenly sampled points without any interpolation.

The key feature of NUST is its doubly adaptive window. 
It adapts to Frequency: It uses a narrow time window to get a clear picture of high-frequency events and a wide time window to accurately measure low-frequency events.

It adapts to Data Density: This is the special part. The window automatically gets wider in parts of your timeline where you have very few data points (to gather more evidence) and narrower where you have lots of data points (to get a more detailed view).

# About This Repository
This repository is organized into two main parts, each in its own Jupyter notebook:

NUST_implementation.ipynb: This is the main development notebook. It contains:

The core implementation of the NUST algorithm and all its helper functions.

A wide range of synthetic signal generators used to create challenging test cases (transients, chirps, bursts, etc.).

Detailed experiments comparing NUST to the S-Transform and the Generalized Lomb-Scargle (GLS) periodogram.

Visualizations explaining the NUST hyperparameters (alpha, gamma, h) and robustness tests.

HD1080.ipynb: This notebook shows a real-world application of NUST. It contains:

The code to load and prepare public radial velocity (RV) data for the exoplanet system HD 10180.

A comparison of the GLS periodogram and the NUST spectrogram on this complex, real-world dataset.

How to Use This Code
Prerequisites
You'll need Python 3 and a few common scientific libraries. You can install all the necessary packages by running:

pip install numpy pandas matplotlib scipy scikit-learn astropy stockwell

Running the Analysis
Clone the Repository:

git clone <your-repo-url>

Add Data: For the HD10180.ipynb notebook, make sure you have the HD_10180_data.csv file in the same directory.

Launch Jupyter: Open a terminal, navigate to the project folder, and run:

jupyter notebook

Run the Notebooks: Open either .ipynb file and run the cells one by one. The code is commented to explain what's happening at each step. The scripts will generate and display all the figures directly in the notebook.
