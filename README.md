# Neural Network Potential (NNP)

This repository contains a framework for training, evaluating, and utilizing Neural Network Potentials, with a specific focus on atomistic simulations of bulk silicon. It integrates machine learning models with the LAMMPS molecular dynamics simulator.

## Project Structure

*   **`NNP.ipynb`**: The main Jupyter Notebook containing the core logic for the Neural Network Potential. This includes data processing, model definition, training, and evaluation.
*   **`lammps/`**: Contains files related to molecular dynamics simulations.
    *   `si.lmp`: The LAMMPS input script configured for running simulations on bulk silicon using the trained potential.
*   **`utils/`**: Helper scripts for data manipulation.
    *   `extract_dump.py`: A Python utility script designed to parse and extract trajectory/atomic data from LAMMPS dump files for analysis or training data generation.
*   **`assets/`**: Contains diagrams and images related to the project.

## Prerequisites

To run this project, you will generally need:

*   Python 3.x
*   Jupyter Notebook / JupyterLab
*   Standard ML libraries (PyTorch)
*   [LAMMPS](https://www.lammps.org/) (compiled with any necessary ML/NNP packages depending on your specific model export format)
*   ASE (Atomic Simulation Environment)

## Usage

1.  **Model Training/Exploration**: Open `NNP.ipynb` to explore the model architecture, train the network on existing dataset files, or evaluate its predictions.
2.  **LAMMPS Simulation**: Navigate to the `lammps/` directory and run the `si.lmp` script using your LAMMPS executable. Ensure the trained model weights are correctly referenced in the script.
    ```bash
    cd lammps
    lmp -in si.lmp
    ```
3.  **Data Extraction**: After running a LAMMPS simulation, use the utility script to process the output dump files.
    ```bash
    python utils/extract_dump.py path/to/your/dumpfile.dump
    ```
