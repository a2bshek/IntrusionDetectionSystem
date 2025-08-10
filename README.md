# DATASET
KDD Cup 1999 dataset by DARPA. The whole dataset can be downloaded from- 

# Intrusion Detection System

This project implements an Intrusion Detection System (IDS) using the [KDD Cup 1999 dataset](http://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html). It includes tools for feature extraction from network traffic and machine learning-based threat detection.

## Project Structure

- **DATASET kddcup99/**  
  Contains the KDD Cup 1999 dataset files used for training and evaluation.

- **FeatureExtraction/**  
  C++ utility for extracting features from network traffic or pcap files, compatible with the KDD '99 dataset format.

- **Threat Detection/**  
  Python notebooks and scripts for building, training, and evaluating classifiers on the extracted features.

## Getting Started

### 1. Dataset

Download the KDD Cup 1999 dataset from [UCI KDD Archive](http://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html) and place the files in the `DATASET kddcup99/` directory.

### 2. Feature Extraction

The feature extraction tool is implemented in C++ in the [`FeatureExtraction`](FeatureExtraction/README.md) directory.

#### Build Instructions (Linux)

1. Create a build directory:
   ```sh
   mkdir build-files
   cd build-files
   ```
2. Generate build files with CMake:
   ```sh
   cmake -DCMAKE_BUILD_TYPE=Debug -G "CodeBlocks - Unix Makefiles" ..
   ```
3. Build the project:
   ```sh
   cd ..
   cmake --build ./build-files --target kdd99extractor -- -j 4
   ```
4. The compiled binary will be at `build-files/src/kdd99extractor`.

For more details, see [FeatureExtraction/README.md](FeatureExtraction/README.md).

### 3. Threat Detection

The [`Threat Detection`](Threat Detection/README.md) directory contains Jupyter notebooks for:

- Data preprocessing
- Model training and evaluation
- Visualization of results

Open the notebooks in JupyterLab or VS Code to run experiments.

## Main Components

- **Sniffer:** Captures and parses network traffic.
- **IP Reassembler:** Handles IP header summaries.
- **Conversation Reconstructor:** Reconstructs network conversations and computes intrinsic features.
- **Statistical Engine:** Computes derived features for machine learning.

## References

- KDD Cup 1999 Data: http://kdd.ics.uci.edu/databases/kddcup99/kddcup99.html
- [Lee, W. & Stolfo, S. J. (2000), 'A framework for constructing features and models for intrusion detection systems'](http://wenke.gtisc.gatech.edu/ids-readings/lee_dmids_frmwk.pdf)
- [Dybey, D. & Dubey, J. (2014), 'A Survey Intrusion Detection with KDD99 Cup Dataset'](http://www.researchpublish.com/download.php?file=A%20Survey%20Intrusion%20Detection%20with%20KDD99-403.pdf&act=book)

## License

For educational and research