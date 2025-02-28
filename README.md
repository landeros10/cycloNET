# CyclNET Image Analysis Package

## Overview

This project directory contains the cycloNET image analysis package, which includes various Python scripts, a saved TensorFlow model, and test image files. The package is designed for analyzing human multiplexed data. This README provides an overview of the directory structure, file descriptions, and instructions for running the analysis.

## Directory Structure and Folder Descriptions

- `app`: Main application directory containing scripts and models.
  - `SavedModel`: Directory containing the saved TensorFlow model.
    - `assets`: Folder for auxiliary files.
    - `saved_model.pb`: The protocol buffer file containing the model architecture and weights.
    - `variables`: Folder containing the model variables.
  - `test_files`: Directory for test files.
    - `HumanSamples_Eval_test2`: Folder for a single human sample for evaluation.
  - `test.py`: Python script for running tests on the model or data.
  - `utils.py`: Python script containing utility functions used across the project.

- `build`: Directory created by the build process, containing build artifacts.
- `dist`: Directory containing the distribution-ready application.
  - `immunoprof`: *** Executable or packaged version of the `immunoprof` application. ***
- `immunoprof.spec`: Specification file for building the `immunoprof` application.
- `README.txt`: This README file.

## Prerequisites
- Python 3.x
- TensorFlow
- NumPy
- Pandas

Install the necessary Python packages using `pip`:
pip install tensorflow numpy pandas

## Usage
### Running the Analysis

To run the analysis on the files in `app/test_files/HumanSamples_Eval_test2`, follow these steps:

1. **Prepare the environment**:
   Navigate to the project directory:

2. **Run the analysis**:
Launch the `dist/immunoprof` application by double clicking or running in a unix terminal

3. **Select a working directory**:
Click the "Browse" button to select the test_files/HumanSamples_Eval_test2 directory and load sample images. Channel names and cycle IDs will be automatically load for this test set but can be inferred either by modifying the cats.txt file in the working directory or by manually inputting channel names under the "Group Samples" section of the GUI.

4. **Select Reference and DAPI channels**
Each analysis cycle needs a reference channel (the channel to which all other images are aligned to, typically CD45 for immune cell analysis), and a DAPI channel. The DAPI channel is used in identifying immune cells boundaries by the neural network.

5 **Begin Analysis**
Click either the "Full Analysis" button or any of the individual steps: "Align Images", "Detect Cell Mask", and "Compute Sums". Check the "Save Aligned Images" box to save a version of the test images that are completely aligned for x-y translations.

6. **Read Data**
Data will be saved in csv format to the working directory in a folder called "data". Use this data to investigate subpopulation clusters and determine immune profiles for your sample.
