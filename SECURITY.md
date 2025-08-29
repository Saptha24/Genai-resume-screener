# Security & Privacy

This project processes sensitive documents (resumes). Follow these guidelines:

- **PII Minimisation**: Do not store raw resumes unless necessary. Prefer anonymised samples for demos.
- **Access Control**: Restrict n8n, Google Sheets, and storage access to authorised users only.
- **Secrets**: Keep API keys and service account JSONs out of Git. Use environment variables or secret managers.
- **Retention**: Delete uploaded resumes after scoring unless you have a lawful basis to retain.
- **Logging**: Log only non-PII operational metadata (timestamps, job ids, status). Avoid logging resume text.
- **Bias Guardrails**: Prompts instruct models to ignore PII (name, gender, nationality, age). Score only job-relevant criteria.
