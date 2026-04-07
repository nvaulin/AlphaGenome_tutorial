# AlphaGenome Tutorial

**Author:** Nikita Vaulin — PhD student, Adameyko lab, Medical University of Vienna  
**Contact:** nikita.vaulin@meduniwien.ac.at · Telegram: [@nvaulin](https://t.me/nvaulin)

---

## What is AlphaGenome?

AlphaGenome is a foundation model developed by Google DeepMind that takes a DNA sequence (up to 1 Mb) as input and simultaneously predicts hundreds of genomic tracks across multiple modalities — including RNA-seq, ATAC-seq, ChIP-seq, splice junctions, and contact maps — for dozens of human and mouse cell types. By learning the cis-regulatory code directly from sequence, AlphaGenome enables zero-shot prediction of gene expression, chromatin accessibility, and variant effects without retraining, making it a powerful tool for interpreting non-coding variation and regulatory genomics at scale.

---

## Notebooks

| # | Notebook | Description |
|---|----------|-------------|
| 1 | [Part 1: Model Exploration](aG_tutorial_1_Exploration.ipynb) | Load the model, explore available output tracks and cell-type metadata |
| 2 | [Part 2: Making Predictions](aG_tutorial_2_Predictions.ipynb) | Predict RNA-seq, ATAC-seq and other tracks for sequences and genomic intervals |
| 3 | [Part 3: Variant Effect Prediction](aG_tutorial_3_Variants.ipynb) | Score single-nucleotide variants and run in silico mutagenesis (ISM) |

---

## Workshop

The workshop consists of two parts:

- **Theoretical** — introduction to AlphaGenome architecture and applications (slides provided separately)
- **Practical** — hands-on Jupyter Notebook sessions (this repository)

For the practical part you will need a **laptop** that can open Jupyter Notebooks.

---

## Setup

### 1. Create the conda environment

Install [miniforge / mamba](https://github.com/conda-forge/miniforge) if you don't have it, then:

```bash
mamba env create -f environment.yml
conda activate alphagenome-env
```

This installs Python 3.11 and `alphagenome==0.6.1` together with all dependencies.

For the full installation guide see: https://www.alphagenomedocs.com/installation.html

### 2. Get an API key

1. Go to https://deepmind.google.com/science/alphagenome/
2. Click the **Get API key** button in the middle of the page
3. Save the key to a plain-text file, e.g.:

```bash
echo "YOUR_API_KEY" > /<your_desired_location>/alphagenome_key.txt
```

The notebooks load the key automatically:

```python
key = open("/<your_desired_location>/alphagenome_key.txt").read().strip()
```

### 3. Launch Jupyter

```bash
conda activate alphagenome-env
jupyter notebook
```

---

## References

- Documentation: https://www.alphagenomedocs.com
- Model page & API key:* https://deepmind.google.com/science/alphagenome/
- Community Forum: https://www.alphagenomecommunity.com/
- Žiga Avsec et al. *Sequence-based genomic prediction with AlphaGenome.* Nature (2025). https://www.nature.com/articles/s41586-025-10014-0

***Extra materials***:
- Tangermeme package: https://github.com/jmschrei/tangermeme
- AlphaGenome model itself: https://github.com/google-deepmind/alphagenome_research
- PyTorch implementaton of AlphaGenome: https://github.com/genomicsxai/alphagenome-pytorch