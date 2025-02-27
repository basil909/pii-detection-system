# SecureScan


[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)](https://github.com/yourusername/securescan)
[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/)

![SecureScan Logo](<https://www.flaticon.com/free-icons/protection )

**SecureScan** is an AI-based solution for detecting and redacting government-issued Personally Identifiable Information (PII) in documents. This tool uses state-of-the-art NLP (powered by [Microsoft DeBERTaV3-Large](https://github.com/microsoft/DeBERTa)) to identify sensitive data such as Aadhaar numbers, PAN, and passport numbers, ensuring your organization remains compliant with privacy regulations.

---

## Problem Statement

Organizations handle large volumes of documents that often contain sensitive PII. Manual redaction is tedious and error-prone. SecureScan automates this process by:

- **Detecting PII:** Using a fine-tuned machine learning model to identify sensitive data.
- **Extracting and Redacting:** Automatically redacting PII from documents (PDFs and images) before they are shared or stored.

---

## Project Overview

SecureScan consists of the following components:

### **Backend API (Python)**
- **Framework:** [FastAPI](https://fastapi.tiangolo.com/)
- **Model:** Fine-tuned **DeBERTaV3-Large** for token classification.
- **OCR:** [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) for image-based text extraction.
- **PDF Processing:** [PyMuPDF (fitz)](https://pymupdf.readthedocs.io/en/latest/) for redaction.

### **Frontend Web App (Next.js)**
- **Framework:** [Next.js](https://nextjs.org/)
- **Styling:** [Tailwind CSS](https://tailwindcss.com/)
- **API Routes:** Node.js backend routes for integrating with the Python API.
- **Interface:** ChatGPT-like interface with options to input text prompts or upload documents/images.

### **Chrome Extension**
- Provides quick access to redaction functionalities directly from the browser.

---

## Why DeBERTaV3-Large?

SecureScan leverages **Microsoft DeBERTaV3-Large** because:

- **Superior Contextual Understanding:**  
  Excels at capturing the context in complex, unstructured documents.
- **Robust Performance:**  
  Achieves state-of-the-art performance on token classification tasks.
- **Adaptability:**  
  Can be fine-tuned on synthetic and real-world data for highly accurate detection of sensitive IDs.

Learn more about [DeBERTaV3 on GitHub](https://github.com/microsoft/DeBERTa).

---

## Installation

### **Backend Setup**

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/yourusername/securescan.git
   cd securescan/backend
