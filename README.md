# Automated Quantum Circuit Dataset Construction

![Python](https://img.shields.io/badge/Python-3.9+-blue)
![NLP](https://img.shields.io/badge/NLP-Enabled-green)
![Computer Vision](https://img.shields.io/badge/Computer%20Vision-OpenCV-orange)
![OCR](https://img.shields.io/badge/OCR-Tesseract-red)
![Dataset](https://img.shields.io/badge/Dataset-Quantum%20Circuits-purple)

A fully automated and reproducible pipeline for extracting **quantum circuit diagrams from scientific papers** and converting them into a **structured image-to-text dataset**.

The system processes **arXiv quantum physics (quant-ph) papers**, detects **quantum circuit diagrams**, extracts **gate information and algorithm descriptions**, and generates **structured metadata for AI research**.

---

# Project Motivation

Quantum computing research papers contain **circuit diagrams describing quantum algorithms**.  
However, these diagrams are embedded inside PDFs and are difficult for machine learning systems to interpret.

This project builds an automated pipeline that:

• extracts circuit diagrams from research papers  
• analyzes their structure using computer vision  
• extracts textual information using OCR  
• produces a structured dataset for AI research

---

# Architecture Overview

```
arXiv Papers (PDF)
        │
        ▼
PDF Processing (PyMuPDF)
        │
        ▼
Image Extraction
        │
        ▼
Image Filtering (OpenCV)
        │
        ▼
OCR Processing (Tesseract)
        │
        ▼
NLP Processing
        │
        ▼
Structured Dataset Generation
```

---

# Pipeline Workflow

### 1. Paper Collection

A list of **quantum physics papers from arXiv (quant-ph)** is used as input.

Example file:

```
paper_list_5.txt
```

---

### 2. PDF Processing

Using **PyMuPDF**, the system extracts:

• raster images  
• vector drawings  

from each PDF page.

---

### 3. Image Filtering

Computer vision heuristics detect **quantum circuit diagrams**.

Filtering techniques include:

• horizontal wire detection  
• line density analysis  
• removal of plots and graphs  
• geometric pattern detection

Implemented with **OpenCV**.

---

### 4. OCR Processing

**Tesseract OCR** extracts text from candidate circuit images.

Extracted information includes:

• gate labels  
• figure annotations  
• algorithm descriptions

---

### 5. NLP Metadata Extraction

Rule-based NLP techniques extract structured information such as:

• quantum gate types  
• algorithm names  
• figure captions  
• descriptive text

Techniques used:

• regex caption parsing  
• keyword-based algorithm inference  
• OCR text analysis

---

### 6. Dataset Generation

The final dataset contains:

• extracted circuit images  
• structured metadata  
• dataset statistics

---

# Dataset Files

| File | Description |
|-----|-------------|
| dataset_5.json | Structured metadata for each circuit |
| paper_list_5.txt | List of processed papers |
| paper_list_counts_5.csv | Dataset statistics |
| documentation_5.pdf | Project report |
| examid_5_tejaswiduptala.ipynb | Implementation notebook |

---

# Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core implementation |
| PyMuPDF | PDF parsing |
| OpenCV | Image processing |
| Tesseract OCR | Text extraction |
| Regex | Caption parsing |
| JSON / CSV | Dataset storage |

---

# Running the Pipeline

Install dependencies:

```
pip install pymupdf opencv-python pillow pytesseract numpy pandas
```

Run the pipeline:

```
python examid_5_tejaswiduptala.ipynb
```

---

# Research Applications

This dataset can support research in:

• quantum circuit recognition  
• scientific diagram understanding  
• vision-language models  
• AI for quantum computing  
• document intelligence systems

---

