# PDF OCR Test Utility (`gitlab_load_file/test.py`)

This module is part of a larger RAG (Retrieval-Augmented Generation) project and is dedicated to testing PDF OCR extraction. It uses a custom pipeline defined in `load_split_file.py` and outputs data in a format compatible with downstream vector storage systems like Pinecone.

## 📁 Folder Structure

```
gitlab_load_file/
├── input_file/               # Folder for test PDF inputs
├── load_split_file.py        # Main logic for OCR + metadata formatting
└── test.py                   # Entry point script for running the test

OCR/
├── images/                   # Processed image outputs
├── config.py
├── image_manager.py
├── image_processor.py
├── main.py                   # Entry point for full OCR pipeline
├── pdf_processor.py          # PDF OCR core logic
├── powerpoint_processor.py   # Not used in this test script
└── storage.py                # AWS S3 upload/management logic
```

## ⚙️ Requirements

* Python 3.12.11
* Install all dependencies:

```bash
pip install -r requirements.txt
```

## 🚀 Running the Test Script

To process a PDF using the OCR test utility:

```bash
python gitlab_load_file/test.py
```

* It will read PDF files from `gitlab_load_file/input_file/`
* It uses `load_split_file.py` to extract and format text/metadata
* Output is printed or saved based on your test implementation

## 🔐 Required Environment Variables

Create a `.env` file at the project root with the following values:

```env
AWS_ACCESS_KEY=your_aws_access_key_here
AWS_SECRET_KEY=your_aws_secret_key_here
AWS_BUCKET_NAME=your_bucket_name_here
MISTRAL_API_KEY=your_mistral_api_key_here
OPENAI_API_KEY=your_openai_api_key_here
```

> Only `AWS_*` values are typically used by the test script for file storage.

## 🧪 Purpose

This utility is built for:

* Testing the OCR extraction on PDF files
* Validating metadata structure (for Pinecone or similar usage)
* Debugging layout, page segmentation, or text recognition issues

## 📝 Notes

* You can place any `.pdf` file inside `input_file/` for testing.
* The script is independent of the main FastAPI backend.
* Modify `test.py` or `load_split_file.py` for custom logic/output.

---

For bugs or improvements, open a PR or issue on the main repo.
