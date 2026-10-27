# 04 â€” Notice-to-rules implementation

1. Validate upload size and content type; scan files before parsing.
2. Extract embedded PDF text. Use OCR for scanned pages and preserve page references/coordinates where possible.
3. Propose structured draft candidates for eligibility, required fields/documents, deadlines, exceptions, and exclusions.
4. Require a page/section citation for each candidate. Mark missing citations, ambiguous wording, and conflicts as unresolved.
5. Show the source notice beside an editable draft for an authorized reviewer.
6. Validate rules against the supported schema and sample cases.
7. On reviewer approval, publish an immutable version with reviewer identity and timestamp. Preserve previous versions and the source hash.
8. If notices conflict or supersede one another, pause the affected rule until a reviewer resolves precedence and effective dates.

The extracted text is a draft interpretation, not authoritative policy. Do not silently activate extracted requirements.

## Required version metadata

Record the source file hash, notice title, issuing authority, scheme, academic year, publication/effective dates, version ID, reviewer identity, approval time, and the version it supersedes. Keep old versions immutable so an application review can be reproduced against the rules active at that time.

## Rule outcomes

- `pass`: the rule found no issue; application still proceeds to human review.
- `correction_needed`: a clear, fixable omission or mismatch; provide the reason and next step.
- `uncertain`: interpretation or evidence is unclear; route to a human reviewer.
- `conflict`: active sources disagree; pause the affected automated check until an authorized reviewer resolves precedence.

Use a typed, allow-listed rule schema and test cases. Never execute arbitrary code or instructions extracted from PDF text.

