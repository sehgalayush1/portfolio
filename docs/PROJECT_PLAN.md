# Static Portfolio Website — Project Plan

## Goal

Create a concise static portfolio that complements the resume and showcases experience and project highlights across all companies.

## Initial direction

- Start with a single-page landing site.
- Use semantic HTML, CSS, and minimal JavaScript.
- Keep the site static; no backend or CMS for the first version.
- Add React or other complexity only if a genuine requirement justifies it.

## Technical direction

- Host the site on Azure Static Web Apps, starting with the Free plan if its current limits fit.
- Keep the code in a personal GitHub repository and use GitHub Actions for deployment; automated code checks are deferred.
- Use one Static Web App resource with `main` as production and temporary pull-request previews; skip a persistent staging environment initially.
- Attach the custom domain and Azure-managed TLS to production; pull-request previews use Azure-provided temporary URLs.
- See [ARCHITECTURE.md](./ARCHITECTURE.md) for the technical decisions, constraints, and remaining questions.

## Phased plan

### Phase 1 — Dummy site and deployment foundation

- Create a minimal placeholder site using HTML, CSS, and simple JavaScript.
- Keep the placeholder generic; do not include real portfolio content yet.
- Put the code in a personal GitHub repository and create an Azure Static Web App.
- Configure GitHub Actions to deploy `main` and create and clean up temporary pull-request previews. Automated code checks are deferred.
- Deploy to the Azure-provided URL. Do not buy or configure a custom domain in this phase.
- **Deliverable:** a working placeholder site on its Azure URL, with production deployment and PR previews verified.

### Phase 2 — Content, design, and portfolio implementation

- Create a separate design document for the portfolio content and visual direction.
- Gather and curate company history, roles, project highlights, outcomes, resume, and contact details; confirm what can be shared publicly.
- Replace the placeholder with the agreed portfolio and implement the design with responsive, accessible HTML and CSS.
- Review changes through pull-request previews and continue deploying to the Azure-provided production URL.
- **Deliverable:** the complete portfolio, reviewed and working on its Azure URL.

### Phase 3 — Custom domain and final release

- Purchase and configure the chosen domain and DNS records.
- Attach the domain to the production environment and confirm Azure-managed TLS is active.
- Run final checks against the custom domain, including HTTPS, navigation, resume link, and contact links.
- **Deliverable:** the finished portfolio released on its custom domain.
