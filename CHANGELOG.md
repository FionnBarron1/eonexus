# Changelog

All notable changes to the EO Nexus site are documented in this file.

Format: `## [MAJOR.MINOR.PATCH.MICRO] - YYYY-MM-DD` with Added / Changed / Fixed / Removed sections.

## [0.0.1.0] - 2026-06-10

### Changed
- Applications submitted through the form now land directly in EO Ireland's HubSpot CRM — each applicant becomes a contact with their name, email, membership tier (derived from revenue band), and company details — replacing the previous Google Sheet feed.
- Applicants now get honest feedback while applying: the button shows "Submitting…" while the application sends, success only appears once HubSpot confirms receipt, and a clear error message appears if something goes wrong (with a more specific prompt when submitted details need correcting).

### Added
- GDPR consent statement displayed above the submit button, matching the consent recorded with each HubSpot submission.
- Google Analytics conversion events for successful and failed application submissions.
- Hidden anti-bot honeypot field to keep junk applications out of the CRM pipeline.
- Submission safeguards: a 15-second timeout so the form never hangs, input length limits, in-flight submissions that survive navigating away, and form handling isolated from the decorative background animation so a rendering glitch can never break applying.
- Development tooling and project documentation for AI-assisted workflows.

### Fixed
- A failed submission after an earlier success no longer shows the success and error banners at the same time.
- The submit button now visibly appears disabled while an application is sending.
- Screen readers now announce submission success and failure messages.
