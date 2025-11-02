# My Website

Obsidian-authored, Hugo-powered portfolio that highlights projects, certifications, active learning, and a running journal.

<p id="top" align="center">
  <a href="#overview">Overview</a> ·
  <a href="#content-map">Content Map</a> ·
  <a href="#docs--automation">Docs &amp; Automation</a> ·
  <a href="#workflow">Workflow</a>
</p>

## Overview
- Showcase professional work with rich case studies and source links.
- Surface current certifications and verification details at a glance.
- Publish long-form articles and short daily journal updates from Obsidian.
- Track ongoing learning goals alongside deployed project updates.
- Automate publishing through Hugo builds and GitHub Actions deployments.

## Content Map
Browse from the repo root to specific content items. Use the links below to drill down, then follow the “Back to top” link to return here.

### Hugo Content (`content/`)
- [Blog](content/blog/) — Long-form posts and thought leadership.
  - [Test Blog 1](content/blog/Test%20Blog%201.md)
- [Journal](content/journal/) — Daily notes and reflections.
  - [Test Journal](content/journal/Test%20Journal.md)
- [Projects](content/projects/) — Highlighted work with supporting links.
  - [Test Links to Project](content/projects/Test%20Links%20to%20Project.md)
- [Certifications](content/certifications/) — Credential metadata and artifacts.
  - [Test Google Cert](content/certifications/Test%20Google%20Cert.md)
  - [Google Advanced Data Analytics Capstone (PDF)](content/certifications/Google%20Advanced%20Data%20Analytics%20Capstone.pdf)

[Back to top](#top)

### Site Assets & Layout
- [layouts/](layouts/) — Hugo templates, partials, and list/single views.
- [static/](static/) — Static files served as-is (images, downloads).
- [assets/](assets/) — Pipeline-managed assets (CSS, JS, images).
- [themes/](themes/) — Third-party or custom Hugo themes (if used).

[Back to top](#top)

### Configuration & Build
- [hugo.toml](hugo.toml) — Global Hugo configuration and menu definitions.
- [archetypes/](archetypes/) — Content archetypes for new pages/posts.
- [i18n/](i18n/) — Localization files.
- [public/](public/) — Generated site output (excluded from commits in production).

[Back to top](#top)

### Documentation (`docs/`)
- [System Plan](docs/system-plan.md) — Obsidian ↔ Hugo automation and layout blueprint.
- [Roadmap](docs/roadmap.md) — Milestone-based delivery plan.

[Back to top](#top)

## Docs & Automation
- **Obsidian Templates** → Define front matter for blog, journal, projects, and certifications (see `docs/system-plan.md`).
- **Sync Script** → Copy or link Obsidian vault folders into Hugo `content/`.
- **CI/CD** → GitHub Actions handles linting, Hugo builds, and deployment to the chosen host.
- **Quality Gates** → Markdown linting, front matter validation, and link checking guard content health.

[Back to top](#top)

## Workflow
1. Draft or update notes inside the Obsidian vault.
2. Run the local sync command so Hugo `content/` mirrors the vault.
3. Preview locally with `hugo server` to confirm layout.
4. Commit and push; GitHub Actions builds and publishes the site automatically.

[Back to top](#top)
