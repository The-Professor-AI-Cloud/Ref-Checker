# Reference Checker

Minimal FastAPI app that extracts in-text citations and reference list entries, matches them, and highlights gaps.

## Setup
- Python 3.12 recommended.
- Install deps: `py -3.12 -m pip install --user fastapi uvicorn jinja2 python-docx python-multipart pytest`.
- Optional: create/activate a virtualenv first.

## Run the app
- Start the server: `py -3.12 -m uvicorn app.main:app --reload --host 127.0.0.1 --port 8000`.
- Open http://127.0.0.1:8000 and upload a `.txt` or `.docx`.
- Download the last run as JSON from http://127.0.0.1:8000/report.json.

## Try with sample docs
- Sample files live in `sample_docs/`: `sample_apa.txt` and `sample_apa.docx`.
- Each contains 6+ in-text citations, one missing reference (`Taylor, 2022`), and one unused reference entry (`Unused, 2016`).
- You can POST directly: `curl -F "file=@sample_docs/sample_apa.txt" http://127.0.0.1:8000/check`.

## Streamlit (for Streamlit Cloud)
- Entry point: `streamlit_app.py`
- Local run: `streamlit run streamlit_app.py`
- Streamlit Cloud will install from `requirements.txt`; ensure the repo includes `sample_docs/` if you want the sample file in the UI.

## Tests
- Run `py -3.12 -m pytest`.
