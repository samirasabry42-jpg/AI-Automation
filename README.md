# FlowSpace

Created by **Samira Sabry**.

A live n8n portfolio for HR policy questions, job applications, career coaching, scheduled CV screening and error monitoring. No fictional responses or demo submissions are included.

## Website

Intended GitHub Pages URL: https://samirasabry42-jpg.github.io/-FlowSpace/ (available after Pages is published).
Repository: https://github.com/samirasabry42-jpg/-FlowSpace

Upload index.html, .nojekyll and the workflows folder at the repository root. Enable Settings > Pages > Deploy from a branch > main > / (root).

## Workflows

1. Intake — form/webhook, validates a CV submission and stores it in Drive and Sheets.
2. Screening — schedule, evaluates pending applications.
3. Monitoring — error trigger and schedules, records failures and sends alerts.
4. HR assistant — chat/webhook, answers using the policy knowledge base.
5. Career coach — form/webhook, prepares a coaching report.

## Import and configure

Import a JSON from workflows into n8n. Connect your own Google Sheets, Drive, Gmail, Groq and Gemini credentials. Replace CONFIGURE_* placeholders. Enable Header Auth for public write webhooks before publishing. Review email recipients before running screening.

## Live architecture and availability

GitHub Pages hosts the single-file HTML frontend. An existing server-side API forwards requests to n8n through ngrok, keeping its token out of the HTML. This adapts the guide's webhook route to the project's existing authenticated workflows. The visitor code is entered by the user and stays in tab memory.

Online/Offline is based on an actual n8n health check, not a fixed badge. A reachable backend does not guarantee every connected Google or AI credential is valid. Forms are disabled offline and when their endpoint is unconfigured.

The backend computer, Docker, n8n and ngrok must be running. HR policy storage is currently temporary; automatic Policy Loader setup and the restart test remain to be completed. Candidate intake, coaching email delivery and the full end-to-end checklist require validation with the owner's accounts before final submission.

Policy uploads and private candidate dashboards are not exposed in the public frontend. Provider tokens, credentials, Google file IDs and candidate records are not included in the public templates.
