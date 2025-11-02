# My Website

Personal portfolio site to showcase professional work, certifications, and long-form writing. The project aims to become a GitHub-hosted website with automated deployments and structured content management for easy updates.

## Objectives
- Present an overview of my background, skills, and current focus.
- Highlight selected projects with rich descriptions, media, and source links.
- Catalogue certifications with metadata (issuer, issue date, verification links).
- Publish blog posts with tagging, RSS feed support, and social sharing previews.
- Automate builds and deployments from GitHub to static hosting.

## Initial Feature Plan
1. **Foundational Layout** – Global navigation, responsive layout system, and landing page hero.
2. **Projects Section** – Cards with filtering, project detail pages, and GitHub integration.
3. **Certifications Section** – Timeline or grid view with credential details and verification links.
4. **Blog** – Markdown-driven posts, tagging, search, and RSS feed.
5. **Contact & Social** – Contact form or mailto link, plus social network badges.
6. **CI/CD Pipeline** – Automated tests, linting, and deploy workflow via GitHub Actions.

## Proposed Tech Stack
- **Framework**: Astro or Next.js (evaluate trade-offs between SSG performance and dynamic needs).
- **Styling**: Tailwind CSS for rapid iteration or a component library if productivity benefits outweigh added weight.
- **Content**: Markdown/MDX for blog posts and certifications; JSON/MD for project metadata.
- **Hosting**: GitHub Pages, Netlify, or Vercel; choose based on desired custom domain and build-time features.

## Repository Structure
```
docs/                    → Planning, architecture notes, and meeting logs
content/
  blog/                  → Blog posts (Markdown/MDX)
  certifications/        → Credential descriptions and metadata
src/
  components/            → Reusable UI components
  pages/                 → Page-level entry points (framework dependent)
public/                  → Static assets (favicons, images, robots.txt)
public/styles/           → Global stylesheets and fonts
scripts/                 → Utility scripts (data transforms, build helpers)
```

## Near-Term Tasks
- Finalize framework choice (Astro vs. Next.js).
- Define content schema for projects, certifications, and blog entries.
- Set up base layout, typography, and theming strategy.
- Draft first round of content (bio, three core projects, two certifications, one blog post outline).
- Configure GitHub Actions workflow for linting and deploy previews.

## Documentation
Additional planning details live in `docs/roadmap.md` and will evolve with the project.
