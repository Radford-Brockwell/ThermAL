# TPBLA_ThermAL

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

![ThermAL Logo](ThermAL.png)

---

## 🔧 Quick Install (dev)

```bash
git clone https://github.com/conor-mckay98/ThermAL
cd ThermAL
python -m pip install -e .
tpbla-thermal
```

---

## 📦 Requirements

- Python 3.8+

Dependencies:

```bash
pip install pandas numpy scipy==1.9.3 scikit-learn==1.2.2 seaborn matplotlib pillow joblib openpyxl
```

---

## 🧪 What is ThermAL?

ThermAL is a **desktop GUI + CLI tool** for predicting regions that stabilise amyloid fibrils.

NOTE: The feature extraction step can be time-limiting for larger sequences. These features are not limited to ThermAL and can be reused for other machine learning tasks.

ThermAL takes one or more FASTA sequences as input, generates all single–residue variants, computes physicochemical features (AAC, DPC, sliding‐window AUC), feeds them into a pre-trained Random Forest model, and produces several output files.  

Key outputs include:

- `Predicted_fitness_with_1_letter_mutations.xlsx`  
- `heatmap_simple.xlsx`  
- `heatmap.png`  
- `sliding_window.xlsx`  
- `sliding_window_with_foldx.png`  

All outputs are written into per-job directories named after each input sequence.

---

## 📁 Project Structure

```
/ThermAL
│
├── required_docs/                  ← precomputed resources
│   ├── 3_B_Atlas.xlsx
│   ├── 3_BT_Atlas.xlsx
│   ├── … (other atlas files)
│   └── ThermAL.joblib
│
├── ThermAL.png                     ← logo displayed in GUI
├── ThermAL.ipynb                   ← example notebook
└── README.md                       ← this file
```

> Make sure all `.xlsx` atlases and the `ThermAL.joblib` model are inside the `required_docs/` folder.

---

## 🚀 Usage

Ensure the `required_docs/` folder (with all `.xlsx` atlases and the model file) is present.

Then launch the GUI:

```bash
tpbla-thermal-gui
```

In the GUI:

1. Click **Select FASTA File** and choose your `.fasta` or `.fa` file.  
2. Click **Run Analysis**.  
3. Watch the progress bars as AAC/DPC and feature-processing steps execute.  
4. When complete, you’ll find one subfolder per sequence in the working directory, each containing exactly the five output files.

---

## 🔍 Outputs (example)

Inside each job folder (named after your FASTA header), you’ll get:

- **Predicted_fitness_with_1_letter_mutations.xlsx** – Full table of variants, predictions, and mutation codes.  
- **heatmap_simple.xlsx** – Pivot table of mean predicted fitness.  
- **heatmap.png** – Visual heatmap (WT cells bordered in black).  
- **sliding_window.xlsx** – Centered 5-residue rolling mean.  
- **sliding_window_with_foldx.png** – Plot highlighting stabilising regions.  

---

## 📬 Contact

Any problems, feel free to reach out:  
📧 conor_mckay98@aol.com  
🔗 [LinkedIn](https://www.linkedin.com/in/conor-mckay-babba7171/)  
