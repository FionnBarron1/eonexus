# EO Nexus

One-page static marketing site for the EO Ireland Accelerator cohort, deployed via GitHub Pages (custom domain in `CNAME`). No build step and no dependencies — edit `index.html` and `styles.css` directly; pushing to `main` deploys.

## Application form / lead flow

The "Apply for Your Spot" form submits straight from the browser to EO Ireland's HubSpot CRM via the public Forms Submission API (portal `8966910`, form `0c940532-366f-4289-98aa-5cc454201603`). There is no server-side code.

How a submission is mapped:

- The applicant's name is split into HubSpot `firstname`/`lastname` (`-` when no last name is given).
- Company, industry, and revenue band are combined into the form's message field; the HubSpot `membership_type` is derived from the revenue band.
- The HubSpot tracking cookie (`hubspotutk`), page URL, and page title are sent as submission context.

Form behaviour:

- The submit button shows "Submitting…" and disables while the request is in flight; success only appears after HubSpot confirms receipt, and a visible error banner (announced to screen readers) appears on failure, with a 15-second timeout so the form never hangs.
- A hidden honeypot field (`website`) silently drops bot submissions.
- A GDPR consent line above the submit button matches the consent text recorded with each HubSpot submission.
- Google Analytics receives a `generate_lead` event on success and `form_submit_error` on failure.

## Project docs

- [CHANGELOG.md](CHANGELOG.md) — release history (current version in [VERSION](VERSION))
- [CLAUDE.md](CLAUDE.md) — AI assistant project instructions and skill routing
