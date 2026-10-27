# 05 â€” Application and document checks

1. Associate each application with the selected scheme and an explicit approved rule-set version.
2. Check required form fields and required document presence first.
3. Extract document text with OCR and normalize values such as names, dates, IDs, and institution names.
4. Compare application values with document values; show exact mismatches and where the evidence appears.
5. Evaluate eligibility and compliance with deterministic, versioned rules.
6. Optionally run visual-integrity models. Return their output as risk signals with uncertainty, not as proof of forgery.
7. Route the results:
   - A clear, fixable omission or incorrect value: show the officer the evidence and a specific correction reason. The officer confirms the return in the portal, and the applicant receives the reason and next step.
   - Checks pass: mark **Ready for human review**.
   - Evidence is ambiguous or a risk signal appears: flag for closer human review.
8. When the applicant corrects and resubmits, run the checks again against the same applicable approved rule version (or the current version if policy requires it).
9. The authorized officer makes and records the final approval or rejection decision in the portal.

Avoid automatic rejection based on a model score. A model trained on a limited set of forged documents may not recognize new forgery techniques or document templates.

