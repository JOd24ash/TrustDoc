# 06 - Optional processing service APIs

A separate backend is not the product; trustDoc is the browser plugin. For the demo, the plugin may use local mock data. A future optional service can handle expensive OCR/model processing or distribute approved rules across authorized officers. The extension UI should remain usable with a mock service and should not depend on a specific AI vendor.

| Method | Endpoint | Purpose |
|---|---|---|
| `POST` | `/api/notices` | Upload/register a notice from the plugin rule setup view |
| `POST` | `/api/notices/{id}/extract` | Start draft rule extraction |
| `POST` | `/api/rule-sets/{id}/approve` | Publish a version after authorized human approval |
| `GET` | `/api/rule-sets` | Fetch approved rule versions available to the officer |
| `POST` | `/api/checks` | Submit the current authorized application fields and selected rule version for checks |
| `GET` | `/api/checks/{checkId}` | Return findings and evidence to the plugin side panel |
| `POST` | `/api/audit-events` | Record a human review action if the portal does not provide an approved audit API |

These routes are a proposed contract, not implemented endpoints. Authenticate the officer, authorize each action by role, validate every request, and minimize sensitive data sent from the extension. Keep personal data and document text out of URLs and routine logs. Use restricted object storage for source documents. Never send portal data to an unapproved service.

