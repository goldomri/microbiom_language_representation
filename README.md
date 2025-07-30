# Microbiome Language Representation – Quick File Guide

| File | Purpose |
|------|---------|
| **supervised_pipeline.ipynb** | End‑to‑end training and evaluation of the supervised body‑site classifier. |
| **supervised_analysis.ipynb** | Generates the tables and figures that summarise the supervised experiment. |
| **unsupervised_pipeline.ipynb** | Learns a masked‑language model on unlabeled taxa “sentences” and writes sample embeddings. |
| **unsupervised_analysis.ipynb** | Visualises and explores the unsupervised embeddings (t‑SNE / clustering metrics). |
| **accuracy_with_different_levels_of_mislabeling.ipynb** | Simulates random label noise and measures how detection accuracy degrades. |

Run each notebook top‑to‑bottom to reproduce the corresponding results and figures. The notebooks are self‑contained and will create any needed sub‑folders (e.g. `models/`, `figures/`, `results/`).

## Required input data

Before executing the notebooks you must supply **biological data** in one of the following formats:

* **MetaPhlAn abundance tables** (`*.tsv`): tab‑separated; first column = taxon path (`k__Bacteria|p__Firmicutes|…`), subsequent columns = relative abundances per sample (values sum to 1). Place these files in `data/raw/`.
* **Raw FASTQ files** (`*.fastq.gz`): organise as `data/fastq/<sample_id>/reads.fastq.gz` and preprocess with MetaPhlAn 4 to generate the abundance tables above.

All notebooks assume that `data/raw/` is populated with one abundance file per sample and will error out if it is empty.

