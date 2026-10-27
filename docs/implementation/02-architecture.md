# 02 - Browser extension architecture

trustDoc is the browser plugin. It adds review assistance to the officer's existing portal; it does not replace that portal with a new application system. Keep the plugin components independent so optional processing services can be replaced later:

- **Extension content script:** reads only current, officer-authorized application fields from the portal page and offers a control to open trustDoc.
- **Extension side panel:** scheme/rule selection, findings, evidence, and review guidance.
- **Extension rule setup/options page:** notice upload, draft review, and approval flow for authorized staff.
- **Notice processor:** PDF text extraction or OCR; proposes requirements with page citations.
- **Rule registry:** stores approved rules, notice metadata, effective periods, and immutable versions. It may be local for a demo or provided by an optional authorized backend for shared rules.
- **Application checker:** performs deterministic completeness, eligibility, deadline, and consistency checks.
- **Document processor:** validates files, extracts text and fields, compares records, and optionally returns visual-risk signals.
- **Review and audit service:** records checks, rule/model versions, officer actions, and timestamps.
- **Notification adapter:** prepares clear, actionable correction reasons for applicants.

The model may propose drafts and explain evidence. It must not publish policy or make final decisions without an officer.

## Suggested review flow

```text
Existing portal page -> Extension content script -> trustDoc side panel
                                              |-> Approved rule set
                                              |-> Application checker
                                              |-> Document processor
                                              |-> Evidence and findings
Officer records final action in the existing portal
```

For the SIH demo, build a mock scholarship portal page and run the extension on it with fictional applications. Do not substitute a standalone review system for the plugin demo.

## Live portal integration

Prefer an official API or approved data exchange if the portal owner provides one. Otherwise, use narrowly scoped extension permissions only after written authorization; read only the current, officer-authorized page. A browser extension does not grant access to protected server records by itself. Do not capture passwords, bypass CAPTCHA/access controls, or submit decisions automatically. Portal page changes may break integration selectors, so each authorized portal adapter needs maintenance.

Any server is an optional processing service for OCR/model execution or shared approved rules, not a separate officer-facing application platform.

