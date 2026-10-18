# Phase 2 - Task Checklist

## Goal

Replace the generic placeholder with a complete portfolio that communicates who you are, highlights your work, and gives visitors a clear next step. Publish and verify it on the existing Azure-generated URL.

Work through one task at a time, confirm its completion criteria, and only then move to the next task. Define the audience and curate the content before choosing the visual design; the strongest project stories should drive the layout.

Keep the single-page static architecture and existing GitHub Actions deployment flow. See [PROJECT_PLAN.md](./PROJECT_PLAN.md) for the phased scope and [ARCHITECTURE.md](./ARCHITECTURE.md) for technical decisions.

## Tasks

### 1. Define the audience and positioning

- [x] Decide the primary audience: hiring managers, engineering peers, potential collaborators, or a mix.
- [x] Define the main message visitors should remember about you.
- [x] Choose the primary visitor action: view your work, download your resume, or contact you.
- [x] Agree a short portfolio brief that captures these decisions.

**Complete when:** the audience, positioning, and primary visitor action are agreed in a short portfolio brief.

### 2. Gather and curate the content

- [ ] Review your resume, company history, roles, and responsibilities.
- [ ] Select a small set of strong project highlights across your experience.
- [ ] Capture each project's problem, your contribution, technical decisions, and outcomes.
- [ ] Gather candidate resume and contact links, and any useful project visuals.
- [ ] Confirm which employer and project details, metrics, and visuals are safe to publish.
- [ ] Approve the content inventory, excluding confidential material and unsupported claims.

**Complete when:** an approved, public-safe content inventory is ready to shape into the page.

### 3. Agree the page structure and write the copy

The starting proposal is a single page with these sections; the final selection and order remain subject to approval:

- **Introduction:** who you are and what you do.
- **Selected work:** a few compelling project stories.
- **Experience:** concise career context, rather than duplicating the entire resume.
- **About:** your interests and approach to engineering.
- **Contact and resume:** clear next steps.

- [ ] Agree the sections, their order, and in-page navigation.
- [ ] Write the introduction and primary call to action.
- [ ] Write the selected project stories, emphasizing your contribution and outcomes.
- [ ] Write concise experience and about copy.
- [ ] Finalize public contact details, resume, and relevant external links.
- [ ] Approve all public-facing copy.

**Complete when:** the page structure, navigation, and public-facing copy are approved.

### 4. Define the visual design

- [ ] Agree typography, colors, spacing, and the overall visual personality.
- [ ] Decide whether photography, diagrams, or project screenshots add value.
- [ ] Define desktop and mobile layouts.
- [ ] Define visible keyboard focus, interaction states, and restrained motion with reduced-motion support.
- [ ] Record the approved portfolio brief, content, page structure, and visual direction in a separate design document.

**Complete when:** an approved design document gives a clear implementation direction.

### 5. Implement the portfolio

- [ ] Replace the generic placeholder with the approved content and design.
- [ ] Use semantic HTML and CSS; add JavaScript only for an agreed requirement.
- [ ] Add approved assets, working resume and contact links, page metadata, and a favicon.
- [ ] Preserve semantic landmarks, heading order, the skip link, explicit navigation labels, and visible keyboard focus.
- [ ] Implement responsive layouts and reduced-motion behavior.
- [ ] Keep asset paths relative to the document root and preserve the existing Azure deployment setup.

**Complete when:** the approved portfolio is implemented and ready for review through an Azure pull-request preview.

### 6. Review through Azure previews

- [ ] Review content accuracy and visual presentation on the deployed pull-request preview.
- [ ] Test keyboard navigation, focus visibility, and in-page navigation targets.
- [ ] Verify resume, contact, and external links, and confirm referenced assets load successfully.
- [ ] Check for browser-console errors and failed requests.
- [ ] Check desktop and mobile layouts down to 320 px, including horizontal overflow.
- [ ] Refine the preview and obtain approval before production deployment.

**Complete when:** the Azure preview is approved, with working links, accessible navigation, responsive layouts, and no browser errors or failed asset requests.

### 7. Publish and verify

- [ ] With explicit authorization to commit and push, submit the approved portfolio through a pull request targeting `main`.
- [ ] Merge the approved pull request and confirm GitHub Actions deploys production successfully.
- [ ] Verify the portfolio at the production Azure URL, including content, assets, navigation, resume, and contact links.
- [ ] Confirm production desktop and mobile layouts, with no horizontal overflow, browser errors, or failed asset requests.
- [ ] Mark Phase 2 complete in the project plan and task checklist.

**Complete when:** the approved portfolio is deployed and verified on the production Azure URL.

## Out of scope and deferred work

- Custom-domain purchase, DNS configuration, Azure-managed TLS validation, and final-domain release checks remain in Phase 3.
- A framework migration, backend, CMS, blog, analytics, or contact-form service is not assumed; each requires a concrete need and an explicit scope decision.
- Automated code checks remain deferred.
