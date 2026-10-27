# 07 - Evaluation plan

Measure each plugin check stage separately; one overall accuracy number can hide important failures.

- **Rule extraction:** field-level precision/recall against reviewer-labeled requirements; track citation correctness and ambiguity handling.
- **OCR and matching:** extraction accuracy by field, document type, language, and scan quality.
- **Document-risk model:** held-out examples separated by source/template to reduce data leakage; report false-positive and false-negative rates as well as precision/recall.
- **Officer workflow:** whether officers can locate evidence quickly and whether correction messages are actionable.
- **Human review:** record overrides and reasons for improvement, with privacy controls; do not assume every historical decision is ground truth.

For an SIH demo, use a small synthetic or explicitly authorized dataset, label its limitations, and show representative successes and errors. Never claim that a model proves authenticity based only on a test-set score.

