# 03 â€” Data contracts

Use validated, versioned JSON (or equivalent typed models). Examples below are illustrative; they do not encode real scholarship policy.

## Rule set

```json
{
  "id": "post-matric-demo",
  "version": 1,
  "scheme": "Example Post-Matric Scholarship",
  "academicYear": "2026-27",
  "source": { "title": "Example notice", "issuer": "Example authority", "fileHash": "sha256:..." },
  "effectiveFrom": "2026-06-01",
  "effectiveTo": "2027-05-31",
  "status": "draft",
  "rules": []
}
```

## Rule

```json
{
  "id": "income-proof-required",
  "kind": "required_document",
  "condition": { "field": "applicant.category", "operator": "in", "value": ["eligible-category"] },
  "expected": { "documentType": "income_certificate" },
  "sourceCitation": { "page": 4, "section": "Eligibility" },
  "severity": "needs_review"
}
```

Never execute arbitrary code extracted from a notice. Allow only supported rule kinds and operators, validate types, and require source citations before approval.

## Check result

Every check result should include a stable ID, outcome (`pass`, `correction_needed`, `uncertain`), plain-language explanation, related rule ID/version, evidence location, and optional model/confidence metadata. Do not rely on one opaque fraud score.

Keep personal applicant data separate from public rule metadata where practical.


