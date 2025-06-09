# Automated Workflow for Processing Construction Tenders and Floor Plans

## 1. Input Verification

- Check if the input PDF is already searchable.
- Use `pdfminer.six` or `PyMuPDF` to extract text from the PDF.
- If no text is detected, apply OCR with Tesseract.

## 2. OCR with Tesseract

- Convert PDF pages to images (using `pdf2image`).
- Extract text using Tesseract OCR (`pytesseract`).
- Save the result in a text file or directly in a variable data structure.

## 3. Vectorization Check of the Floor Plan

- Check the file format of the floor plan (PDF, SVG, DXF).
- If PDF:
  - Check if vector paths are present (e.g., using `PyMuPDF`).
- If raster image or PDF without vectors:
  - Convert raster image to binary image with OpenCV.
  - Vectorize with Potrace and save as SVG.

## 4. Text Analysis and Information Extraction

- Use NLP (e.g., spaCy) to extract relevant keywords (positions, materials, tasks).
- Structure the extracted information in tabular form (e.g., with pandas).

## 5. Automated Annotation of the Floor Plan

- Load the floor plan (SVG) with a suitable Python library (e.g., `svgwrite`, `matplotlib`).
- Place automatically generated annotations.
- Apply position or room recognition (optionally using pattern recognition or AI-based segmentation with LayoutParser or YOLO).
- Save the annotated plan as a PDF.

## 6. Improvements & Extensions (Optional)

- Integration of AI-based segmentation for more precise positioning.
- Automatic creation of a summary (Generative AI with GPT-API).
- Interface to external databases or ERP systems for direct further processing.

## Implementation in Jupyter Notebook

- Modular and clearly separated functions for each workflow step.
- Integrated visual validation steps for quality control.

---

> **This workflow is scalable, automated, and flexible, enabling easy adjustments and offering a high degree of automation through intelligent pre-checks and AI-assisted annotations.**