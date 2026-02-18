# CardTracker — Architecture Overview (Sanitized)

Flask-based backend system implementing structured ingestion, normalization, and ROI evaluation workflows for large-scale trading card datasets.  
(Code sample only — no private data, API keys, or proprietary logic included.)

---

## System Architecture

Raw Input (Card Data / Image Metadata)
        ↓
Structured Ingestion & Normalization
        ↓
Validation & Heuristic Scoring Layer
        ↓
Pricing & ROI Computation
        ↓
Relational Storage
        ↓
Dashboard Interface

---

## Engineering Focus

- Structured ingestion and normalization of raw card records  
- JSON/data validation and malformed input handling  
- Outlier detection for pricing reliability (`trim_outliers`)  
- Blended market price computation (`blended_price`)  
- ROI calculation pipeline (`roi_pct`)  
- Heuristic grading engine returning normalized score + band  
- Clear separation of concerns across ingest, pricing, and grading layers  
- Pytest validation suite for deterministic behavior  
- Designed to support batch-oriented workflows and structured data enforcement prior to relational persistence  

---

## Key Modules

### app/ingest/session.py  
Cleans and normalizes raw card rows prior to processing  

### app/roi/pricing.py  
- `trim_outliers()`  
- `blended_price()`  
- `roi_pct()`  

### app/grading/heuristics.py  
Returns normalized grading score and classification band  

---

## Local Execution

Run locally:

python app/cardtracker_app.py

Open:
http://127.0.0.1:5099/dash

Run tests:

pytest -q
