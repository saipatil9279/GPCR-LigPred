GPCR-LigPred is a command-line interface (CLI) based tool that takes a FASTA file of one or more GPCR sequences and predicts, for each sequence, whether it is likely to bind a small molecule or a peptide.

This uses two pre-trained LightGBM models:
- A k-mer Word2Vec-based model
- An AminoAcidIndex (AAIndex) based model

This repository hosts the built .whl file and configuration needed to install the tool locally.

Prerequisites: 
The wheel bundles dependencies in pyproject.toml. Required packages include:
- Python ≥ 3.9
- numpy
- pandas
- biopython
- gensim ≥ 4.0
- lightgbm

System Dependencies (for SciPy / LightGBM builds)

Some dependencies (like SciPy) require system-level libraries. Please install them beforehand if your system doesn’t have them.

- For Linux (Debian/Ubuntu-based):

sudo apt-get update

sudo apt-get install libopenblas-dev cmake pkg-config gfortran -y

- For MacOS:

brew install openblas cmake pkg-config gfortran

- For Windows:

Install Microsoft C++ Build Tools (required for some scientific Python libraries).

Alternatively, use Anaconda/Miniconda, which comes with precompiled scientific libraries and avoids compiler issues.


Installation: 

Since the package is not yet published to PyPI, you have two options. 

- You can install it directly from the provided wheel (Recommended)

pip install gpcr_predict-0.1.0-py3-none-any.whl

Just make sure you are inside the directory containing the .whl file, or provide the full path to it.

- Clone the repository and install locally

git clone https://github.com/saipatil9279/GPCR-LigPred.git

cd GPCR-LigPred

pip install gpcr_predict-0.1.0-py3-none-any.whl

You can verify the installation using:

pip show gpcr-predict


Usage: 

In the CLI Mode

Once installed, you can run predictions directly from the command line:

gpcr-predict input_sequences.fasta --output predictions.csv

Where, 

input_sequences.fasta: FASTA file with one or more GPCR sequences.

--output: Path to save predictions as a CSV.

For example: gpcr-predict test.fasta --output results.csv

Notes:

If gpcr-predict command is not recognized, make sure your Python Scripts directory is in your PATH.

Example for Windows:

C:\Users\<USER>\AppData\Local\Programs\Python\Python311\Scripts

On Linux/macOS, ensure ~/.local/bin or your virtual environment’s bin/ directory is in your PATH.











