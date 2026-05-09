# CardTracker — Sanitized Architecture Sample

Flask-based backend system implementing structured ingestion, normalization, pricing analysis, and ROI evaluation workflows for large-scale trading card datasets.

> Sanitized engineering sample only — no private data, API keys, proprietary assets, or production logic included.

---

## Architecture Pipeline

```text
Raw Input (Card Data / Image Metadata)
        ↓
Structured Ingestion & Normalization
        ↓
Validation & Heuristic Scoring
        ↓
Pricing & ROI Computation
        ↓
Relational Storage
        ↓
Dashboard Interface

Technical Highlights
Structured ingestion and normalization pipelines
JSON/data validation and malformed input handling
Outlier detection for pricing reliability
Blended market price computation
ROI calculation workflows
Heuristic grading and classification logic
Layered separation of ingest, pricing, and grading systems
Deterministic Pytest validation suite
Batch-oriented processing and structured persistence enforcement
Core Modules
app/ingest/session.py

Cleans and normalizes raw card rows prior to downstream processing.

app/roi/pricing.py

Functions:

trim_outliers()
blended_price()
roi_pct()
app/grading/heuristics.py

Returns normalized grading scores and classification bands.

Getting Started
Install Dependencies
pip install -r requirements.txt
Run Application
python app/cardtracker_app.py

Open dashboard:

http://127.0.0.1:5099/dash
Run Tests
pytest -q
Sanitization Notice

This repository intentionally excludes:

Production datasets
API credentials
Proprietary pricing sources
Sensitive business logic
Private collection assets

The purpose of this repository is to demonstrate backend architecture, data workflows, and engineering structure only.

License

Released under the MIT License.
