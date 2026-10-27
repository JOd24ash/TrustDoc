# 09 - SIH plugin demo acceptance criteria

The browser-extension demo is ready when:

- The extension loads on a mock scholarship portal page with fictional applicant data.
- The plugin's rule setup view can show a sample official-style notice as a cited draft rule set.
- An authorized reviewer can edit, approve, and activate a rule version.
- At least three fictional applications show `pass`, `correction_needed`, and `uncertain` outcomes in the plugin side panel.
- Every finding points to its source rule or document evidence.
- Incorrect or incomplete applications can be returned by the officer with a clear correction reason; the demo shows the applicant resubmitting for another check.
- The officer can record a final mock action; no AI result silently approves or rejects an application.
- The interface labels simulated behavior and sends no real data to a server.

## Demo data safeguards

Use fictional applicants, synthetic notices, and generated/sample documents. Do not put Aadhaar numbers, bank details, real student records, or genuine forged documents in the demo unless the team has explicit authorization and secure handling arrangements.

## Suggested plugin build milestones

1. Create a mock scholarship portal page with a few fictional applications.
2. Build the browser extension shell and side panel; let it read mock-page fields.
3. Add a plugin rule setup view for uploading and reviewing one sample notice.
4. Add the approved rule-set fixture and deterministic form checks.
5. Show explainable evidence and applicant correction text in the side panel.
6. Add OCR and mismatch checks; evaluate a visual model only after securing representative authorized examples.
7. Consider an optional processing service and live portal integration only after authorization and privacy review.

