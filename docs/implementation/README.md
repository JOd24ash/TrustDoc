# Browser plugin implementation guides

These documents describe how to build trustDoc as an officer-side browser plugin. The current checkout contains documentation only; extension source code has not been implemented yet. Any backend described is an optional service used by the plugin.

1. [SIH demo scope](./01-demo-scope.md)
2. [Browser extension architecture and portal integration](./02-architecture.md)
3. [Data contracts](./03-data-contracts.md)
4. [Notice-to-rules extraction, approval, and versioning](./04-notice-to-rules.md)
5. [Application and document checks](./05-application-document-checks.md)
6. [Optional API and processing backend](./06-api-backend.md)
7. [Evaluation plan](./07-evaluation.md)
8. [Security and privacy](./08-security-and-privacy.md)
9. [SIH demo acceptance criteria](./09-demo-acceptance.md)

## Recommended build order

Start with an unpacked browser extension and a mock scholarship portal page using synthetic data. Add a plugin rule-setup view for one notice and human-approved rule set, then check the mock portal's current application in the extension side panel. Add OCR and document analysis after the interaction is clear. Consider live portal access only after the portal owner authorizes it.

