# Personalizing CML Treatment with a Hybrid Quantum-Classical Stack

**Author:** Venkata Shashish Vasireddi
**Affiliation:** Heritage High School / Harvard Undergraduate OpenBio Laboratory
**Mentor:** Collin Szczepanski (Columbia University)

## Project Overview

This project implements a hybrid pipeline utilizing quantum computing and classical machine learning to identify optimal pharmacological treatments for Chronic Myeloid Leukemia (CML).

The pipeline targets the BCR::ABL1 oncogene and operates in two distinct stages:
1. **Quantum Molecular Docking:** Utilizes the Quantum Approximate Optimization Algorithm (QAOA) to simulate ligand-protein interaction and calculate binding strength.
2. **Classical ADMET Profiling:** Uses Deep Learning (ADMET-AI) to predict the safety profile of candidate drugs, filtering for toxicity and absorption properties.

## File Descriptions

* **Finalcode_1(QAOA).ipynb**
  The quantum computing notebook. It accepts a protein structure (PDB) and ligand SMILES strings. It constructs a Binding Interaction Graph (BIG) and solves the Maximum Weighted Clique problem using QAOA via NVIDIA CUDA-Q to derive a binding score.

* **Finalcode_2(ADMET).ipynb**
  The safety analysis notebook. It takes the binding scores generated in the first notebook and processes the ligands through an ADMET prediction model. It ranks the drugs based on a combination of efficacy (binding score) and safety (blood-brain barrier penetration, cardiotoxicity, etc.).

* **Manuscript.docx / Poster.pptx**
  These files contain the project background, methodology, and detailed discussion of the results.

## Requirements

This project is optimized for a Google Colab environment with a GPU runtime (T4 recommended).

**Primary Dependencies:**
* cudaq (NVIDIA CUDA Quantum)
* rdkit (Cheminformatics)
* Bio (Biopython)
* admet_ai (ADMET prediction)
* torch (PyTorch)

To install dependencies, run:
```bash
pip install rdkit Bio cudaq admet_ai torch
