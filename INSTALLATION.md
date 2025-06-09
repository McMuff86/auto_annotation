# Installation Guide for auto_annotation Environment

This guide describes step by step how to set up the Python environment for the auto_annotation project, including all required modules. Use these instructions if you need to recreate the environment from scratch.

---

## 1. Remove old environment (if exists)

```powershell
conda deactivate
conda remove -n auto_annotation --all --yes
```

---

## 2. Create new environment

```powershell
conda create -n auto_annotation python=3.11 --yes
conda activate auto_annotation
```

---

## 3. Install packages with conda

```powershell
conda install numpy opencv pandas jupyter matplotlib --yes
```

---

## 4. Install remaining packages with pip

```powershell
pip install pymupdf pdf2image pytesseract spacy layoutparser yolov5 svgwrite
```

---

## 5. Install spaCy German language model

```powershell
python -m spacy download de_core_news_lg
```

---

## 6. Install Tesseract-OCR (Windows program)

- Download and install from: https://github.com/tesseract-ocr/tesseract/wiki
- Make sure the path to `tesseract.exe` is correct in your scripts (usually `C:\Program Files\Tesseract-OCR\tesseract.exe`).

---

## 7. (Optional) Check installation

You can use the `test_installation.ipynb` notebook to verify that all modules are installed and working correctly.

---

**Tip:**
If you need to install additional modules, always prefer `conda` for large packages (like numpy, opencv, pandas) and use `pip` for the rest. 