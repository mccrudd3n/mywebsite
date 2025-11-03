# My Website

Obsidian-authored, Hugo-powered portfolio that highlights shipped projects, certifications, learning goals, and a day-to-day journal.

<p id="top" align="center">
  <a href="#overview">Overview</a> ·
  <a href="#site-navigation">Site Navigation</a> ·
  <a href="#repository-structure">Repository Structure</a> ·
  <a href="#deployment-workflow">Deployment Workflow</a> ·
  <a href="#authoring-workflow">Authoring Workflow</a>
</p>

## Overview
- Presents core projects, certifications, long-form blog posts, and short journal updates.
- Built with Hugo; layout templates provide persistent navigation back to root sections.
- Obsidian remains the primary writing surface, with content synced directly into `content/`.
- GitHub Pages ready: navigation URLs resolve from the configured `baseURL`.

## Site Navigation
The Hugo layout templates read the `main` menu defined in `hugo.toml`, rendering a persistent navigation bar (Home, Projects, Certifications, Blog, Journal) on every page. Each leaf page also exposes contextual “Back to Home” and “Back to &lt;Section&gt;” links to keep readers oriented.

Assuming GitHub Pages deployment at `https://lostuser.github.io/mywebsite/`, the live paths are:

- Home → `/` &nbsp;(`content/_index.md`)
- Projects → `/projects/` &nbsp;(`content/projects/`)
  - Sample: [Test Links to Project](content/projects/Test%20Links%20to%20Project.md)
- Certifications → `/certifications/` &nbsp;(`content/certifications/`)
  - Sample: [Test Google Cert](content/certifications/Test%20Google%20Cert.md)
  - Artifact: [Google Advanced Data Analytics Capstone (PDF)](content/certifications/Google%20Advanced%20Data%20Analytics%20Capstone.pdf)
- Blog → `/blog/` &nbsp;(`content/blog/`)
  - Sample: [Test Blog 1](content/blog/Test%20Blog%201.md)
- Journal → `/journal/` &nbsp;(`content/journal/`)
  - Sample: [Test Journal](content/journal/Test%20Journal.md)

Update the `baseURL` in `hugo.toml` if deploying to a different domain; the navigation menu will automatically render correct paths for the chosen host.

## Repository Structure
```
content/                 → Hugo sections (blog, journal, projects, certifications)
layouts/                 → Base template, section lists, and single-page views with navigation
static/                  → Static assets served without processing
assets/                  → Pipeline-managed styles/scripts (optional)
docs/                    → Planning docs (system plan, roadmap)
hugo.toml                → Hugo configuration and menu definitions
```

## Deployment Workflow
1. Configure GitHub Pages (project site): Settings → Pages → GitHub Actions.
2. Add a GitHub Actions workflow (e.g., `.github/workflows/deploy.yml`) that:
   - Checks out the repo
   - Runs `hugo --minify`
   - Deploys the `public/` output to the `gh-pages` branch (or Pages artifact)
3. Ensure `baseURL` points at the Pages URL (`https://lostuser.github.io/mywebsite/` by default).
4. Commit and push; each merge to `main` will rebuild and publish the site with the correct navigation paths.

> Tip: If you serve the site from a custom domain, update `baseURL` and add the domain to `static/CNAME`.

## Authoring Workflow
1. Draft or update notes in Obsidian using the front-matter templates documented in `docs/system-plan.md`.
2. Run your sync command to copy the vault into Hugo’s `content/` directories.
3. Preview locally with `hugo server` to confirm navigation and linking.
4. Commit and push; GitHub Actions handles the production build and deployment.

### Image Embeds
- Store shared assets under `static/images/` and include them with `{{< staticimg src="images/example.png" alt="Descriptive alt text" >}}`; the shortcode adds the correct `/mywebsite/` prefix for GitHub Pages.
- Alternatively, use page bundles (`content/blog/my-post/index.md` + image files) and reference them with standard Markdown (`![Alt text](cover.jpg)`). The custom image render hook resolves bundle assets automatically.

### Documentation
- [System Plan](docs/system-plan.md) — Obsidian ↔ Hugo automation, layout details, and maintenance cadence.
- [Roadmap](docs/roadmap.md) — Milestones for content, design polish, and automation.
