# Data Annotation Quality Audit Pipeline

A simulated end-to-end pipeline for the kind of work ML data teams do:
generating labeled data, comparing annotators, and auditing quality —
similar to Amazon's ML Data Associate annotation and QA workflow.

## What this project does
1. Generates a raw dataset (300 items with captions and categories) — generate_sample_data.py
2. Simulates two independent human annotators labeling the same data with realistic accuracy levels — simulate_annotators.py
3. Runs a quality audit comparing both annotators against each other and against ground truth — quality_audit.py

## Key concepts demonstrated
- Inter-annotator agreement using Cohen's Kappa
- Quality auditing: flagging disagreements into a review queue
- Accuracy tracking per annotator
- SOP-style reporting

## How to run
pip install pandas scikit-learn
python3 generate_sample_data.py
python3 simulate_annotators.py
python3 quality_audit.py

## Sample output
Total items reviewed:            300
Annotator A accuracy:            91.00%
Annotator B accuracy:            83.33%
Raw agreement rate (A vs B):     74.67%
Cohen's Kappa (A vs B):          0.695
Interpretation:                  Substantial agreement
Items flagged for manual review: 76

# Text Data Quality & Grammar Validation Tool

A rule-based + NLP-assisted tool for validating text data quality.

## What this project does
1. Generates sample text data with intentional issues — sample_text_data.py
2. Runs rule-based quality checks — text_quality_checker.py
3. Adds NLP linguistic analysis using spaCy — spacy_analysis.py

## Checks performed
- Empty / too-short entries
- Extra or leading/trailing whitespace
- Casing issues
- Duplicate text detection
- Common grammar mistakes

## How to run
pip install spacy
python -m spacy download en_core_web_sm
python3 sample_text_data.py
python3 text_quality_checker.py
python3 spacy_analysis.py

## Sample output
Total samples checked:    15
Clean samples:            3 (20.0%)
Flagged samples:          12 (80.0%)
