# EO Nexus

One-page static marketing site for the EO Ireland Accelerator cohort, deployed via GitHub Pages (see CNAME). No build step — edit `index.html` and `styles.css` directly.

The application form posts to EO Ireland's HubSpot portal 8966910 (form `0c940532-366f-4289-98aa-5cc454201603`) via the public Forms Submission API.

## Skill routing

When the user's request matches an available skill, invoke it via the Skill tool. When in doubt, invoke the skill.

Key routing rules:
- Product ideas/brainstorming → invoke /office-hours
- Strategy/scope → invoke /plan-ceo-review
- Architecture → invoke /plan-eng-review
- Design system/plan review → invoke /design-consultation or /plan-design-review
- Full review pipeline → invoke /autoplan
- Bugs/errors → invoke /investigate
- QA/testing site behavior → invoke /qa or /qa-only
- Code review/diff check → invoke /review
- Visual polish → invoke /design-review
- Ship/deploy/PR → invoke /ship or /land-and-deploy
- Save progress → invoke /context-save
- Resume context → invoke /context-restore
- Author a backlog-ready spec/issue → invoke /spec
