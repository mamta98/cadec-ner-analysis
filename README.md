# cadec-ner-analysis

# CADEC NER Analysis

This repository contains a Jupyter notebook and supporting code that performs named entity recognition (NER) analysis and evaluation on the CADEC dataset.

## Tasks Completed
 Enumerate distinct entities of each label type (ADR, Drug, Disease, Symptom) and report counts.  
 Use a Hugging Face transformer model (`d4data/biomedical-ner-all`) to label forum posts in BIO format and convert them to CADEC’s format.  
 Measure model performance (precision, recall, F1) against ground truth annotations in `original/`, with justification of metric choice (standard for NER: F1 balances precision and   recall).  
 Measure ADR-specific performance against `meddra/` ground truth annotations.  
 Evaluate model performance on 50 random forum posts.  
 Combine `original/` and `sct/` annotations to map text spans to SNOMED CT codes and descriptions, and compare two matching strategies: approximate string matching and embedding-based  similarity.

## Repository Structure
- `notebook.ipynb` — The main Jupyter notebook with all code and outputs.
- `data/` — Directory containing CADEC dataset subdirectories: `text/`, `original/`, `meddra/`, `sct/`.
- Work with the CADEC dataset, which is available in a ZIP file called CADEC.v2.zip, from the CADEC dataset repository.
- `README.md` — This file.

## Requirements
- Python 3.8+
- Libraries: `transformers`, `sentence-transformers`, `pandas`, `tqdm`, `rapidfuzz`


## Notes
- F1 was chosen as the main metric because it balances precision (correctness of predictions) and recall (coverage of ground truth). This is critical in NER for imbalanced data like ADR mentions.
- Embedding similarity was implemented with `sentence-transformers` for better semantic matching of ADR mentions to
