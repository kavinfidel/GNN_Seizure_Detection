# Epileptic Seizure Detection using Graph Neural Networks

This repository contains the data and code used for the detection of epileptic seizures using Graph Neural Network (GNN) models. The dataset has been pre-processed into graph structures, with adjacency matrices representing the connections between nodes (EEG channels) and feature vectors capturing various signal characteristics for each node.

## Repository Structure

### 1. Data Folders
The data was extracted from 366 `.edf` files from CHB-MIT dataset using the 'wfdb' package(code for this will be uploaded later)

Properties of the Data:
Sampling Frequency: 256 Hz

Duration of Non-Seizure Recordings: 90 seconds (due to the number of files and limited computational resources)

Duration of Seizure Recordings: From 10 seconds before the onset of the seizure to 10 seconds after the seizure ends.

Node Features:
- Mean
- Standard Deviation
- Skewness
- Kurtosis
- Absolute Bandpower of each frequency band
  
There are two main data folders:
- **Adjacency Matrix**: Contains the adjacency matrices in `.npy` format, representing graph edges.
- **Features**: Contains the node feature vectors for each graph in `.csv` format, organized by feature extraction methods.

Each folder is further divided into subfolders:
- **Seizure**: Contains graphs labeled as seizure data.
- **Non-Seizure**: Contains graphs labeled as non-seizure data.

### 2. Adjacency Matrix Folder
- This folder holds the graph edge data stored in `.npy` format.
- Two subfolders:
  - `Seizure`: Contains adjacency matrices for seizure events.
  - `Non-Seizure`: Contains adjacency matrices for non-seizure events.

### 3. Features Folder
- Contains the node feature vectors extracted from EEG data.
- Two subfolders:
  - **abs&zeroc**: Node features include zero crossing as one of the features.
    - `Seizure`: Contains node features for seizure events.
    - `Non-Seizure`: Contains node features for non-seizure events.
  - **absolute**: Node features without zero crossing.
    - `Seizure`: Contains node features for seizure events.
    - `Non-Seizure`: Contains node features for non-seizure events.

## Usage

The subfolder structure within the `adjacency_matrix` and `features` folders helps in organizing the data for easier loading. Each folder corresponds to specific conditions (seizure vs. non-seizure) and feature extraction methods (with or without zero crossing).

## GNN Models
- This repository also includes code for training and evaluating Graph Neural Network models (GCN, GIN, GAT, GraphSAGE) for seizure detection.
- Best performming models are stored in the 'Best_models' folder

