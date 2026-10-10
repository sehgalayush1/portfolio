# Phase 1 — Task Checklist

## Goal

Build and publish a generic placeholder site to an Azure Static Web Apps URL, then establish GitHub Actions CI/CD. Work through one task at a time, confirm its completion criteria, and only then move to the next task.

Phase 1 is limited to validating the static-site and deployment setup. Real portfolio content, visual design, and a custom domain are deferred to later phases.

## Tasks

### 1. Build the placeholder site locally

- [x] Create the initial static site in this repository with HTML, CSS, and simple JavaScript as needed.
- [x] Keep the page generic; do not add personal, company, or project information.
- [x] Avoid adding a framework, backend, or build system unless required.
- [x] Add a project README with local run instructions.

**Complete when:** the site source and README are present locally, ready for browser testing.

### 2. Test the local site in a browser

- [x] Run the site with a local static web server.
- [x] Open it in a browser and check the page at desktop and mobile viewport sizes.
- [x] Check that styles and referenced assets load, navigation links work, and the browser console has no errors.
- [x] Fix any issues found before continuing.

**Complete when:** the local placeholder works in the browser and has been reviewed.

### 3. Create a personal GitHub repository and push the code

- [x] Connect to the user's personal GitHub account using GitHub CLI.
- [x] Create the public `portfolio` repository.
- [x] Push the locally tested code to the `main` branch.

**Created:** [sehgalayush1/portfolio](https://github.com/sehgalayush1/portfolio) (public, default branch: `main`).

**Complete when:** the GitHub repository contains the tested site and its latest commit is available remotely.

### 4. Create an Azure Static Web App and deploy locally

- [ ] Connect to the user's Azure account.
- [ ] Create a new Azure Static Web Apps resource, initially using the Free plan if suitable.
- [ ] Deploy the local site to the resource without relying on GitHub Actions yet.
- [ ] Use the Azure-generated URL; do not configure or purchase a custom domain in this phase.
- [ ] Store any deployment credentials securely and do not add them to the repository.

**Complete when:** a deployment from the local project succeeds and Azure provides the app's default URL.

### 5. Verify the Azure deployment

- [ ] Open the Azure-generated URL in a browser.
- [ ] Confirm the deployed page, styles, scripts, and interactions match the locally tested version.
- [ ] Check desktop and mobile layouts, browser-console errors, and failed asset requests.
- [ ] Fix and redeploy any issues found.

**Complete when:** the placeholder has been verified working at its Azure URL.

### 6. Add GitHub Actions CI/CD

- [ ] Add a GitHub Actions workflow to the repository for Azure Static Web Apps.
- [ ] Configure the workflow to run the agreed checks and deploy the production branch.
- [ ] Configure pull-request preview deployments and cleanup when a pull request closes.
- [ ] Store the Azure deployment token as a GitHub Actions secret, not in workflow source.
- [ ] Run the workflow and verify both a production deployment and a pull-request preview.

**Complete when:** GitHub Actions successfully deploys production changes and creates and removes pull-request previews as expected.

## Deferred to later phases

- Real portfolio content and final visual design (Phase 2).
- Buying or configuring a custom domain and validating the final release (Phase 3).
