# trustDoc - officer-side browser plugin

trustDoc is a proposed browser plugin that assists authorized officers while they review applications in an existing scholarship or government portal. It reads the current application page with permission, checks the application against selected, human-approved notice rules, and displays document and compliance findings in a side panel. The officer makes the final decision in the portal.

This folder currently contains project documentation only. The browser-extension source code is not present yet, so there is no runnable plugin in this checkout.

## Problem statement

**SIH26261: AI-Powered Application Validation, Document Authentication and Regulatory Compliance Verification.** trustDoc addresses this through reusable, human-approved rules and an officer-side browser plugin.

## Plugin workflow

1. An authorized staff member opens the plugin's rule setup view and uploads an official notice.
2. The plugin extracts draft eligibility criteria, required fields/documents, dates, and exceptions, citing source pages.
3. An authorized reviewer checks the draft against the notice and approves a version.
4. An officer opens an application in the existing portal and selects the scheme/rule version in the plugin side panel.
5. The plugin checks visible form fields, rules, cross-document consistency, and possible document-integrity signals.
6. It shows findings with evidence and explains each flag.
7. If information is missing or incorrect, the officer returns the application to the applicant with a specific correction reason. After resubmission, the plugin checks it again. Passing or uncertain applications go to officer review.
8. The officer records the final decision in the existing portal.

## Implementation documentation

Start with the [implementation guide](./docs/implementation/README.md). It links to the plugin architecture, rule lifecycle, data contracts, application checks, optional backend, evaluation, security, and demo acceptance criteria.

## Safety and scope

AI flags are screening signals, not proof that a document is forged. Rule extraction produces drafts; staff approve them before use. Use synthetic or authorized data. A live portal integration requires approval from its owner and an authorized access method. Any backend is an optional processing service for the plugin, not a separate officer-facing application system.

