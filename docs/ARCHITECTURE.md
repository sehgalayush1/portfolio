# Static Portfolio Website — Architecture

## Status

Initial technical direction, discussed on 2026-10-10. Recheck Azure plan pricing and quotas when provisioning resources.

## Goals and constraints

- Build a concise static portfolio to complement the resume.
- Start with semantic HTML, CSS, and minimal JavaScript.
- Avoid a framework, backend, or CMS unless a concrete requirement justifies one.
- Keep site content and visual design decisions for a separate design document.

## Hosting and repository

- Store the source in a personal GitHub repository.
- Host the site with Azure Static Web Apps.
- Start with the Free plan if its current limits remain suitable for the project.
- Use Microsoft's `Azure/static-web-apps-deploy` GitHub Action for deployment.
- Keep the static site in `src/` and configure `app_location: "src"` in the deployment workflow. Leave `api_location` unset and omit `output_location` unless an API or build step is introduced.

## Environments and deployment flow

Use a single Azure Static Web Apps resource, with no persistent staging environment initially:

- **Production:** Deploy the `main` branch to the production environment.
- **Pull-request previews:** Pull requests targeting `main` get temporary preview environments. Updates to a pull request refresh its preview; closing the pull request removes that environment.

The deployment flow is:

1. Create a feature branch from `main` and open a pull request targeting `main`.
2. GitHub Actions runs the agreed validation checks and deploys the pull request to its preview URL.
3. Review and test the preview. New commits to the pull request update that preview.
4. Merge the approved pull request to `main` to deploy the change to production.

Configure the workflow to identify `main` as the production branch and trigger on pushes to `main` and the relevant pull-request events.

This provides a place to test each change before it goes live. A persistent staging environment can be added later if changes need to be tested together on a stable shared URL before production.

## Custom domain and TLS

- Attach the custom domain to the production environment.
- Azure Static Web Apps automatically provisions and renews free TLS certificates for the default and configured custom domains.
- Domain registration and renewal are separate from the Azure-managed TLS certificate.
- Preview environments do not support custom domains. Pull-request previews use Azure-provided temporary URLs.
- Choose the canonical public hostname and configure the appropriate DNS records before launch.

## Limits and trade-offs

- The Free plan quota currently lists up to three preview environments per app. With no persistent staging environment, that allows up to three concurrent pull-request previews.
- Preview environments are not geo-distributed.
- If a stable shared staging URL is needed later, a persistent branch-preview environment can be added to this resource. If staging needs a custom domain or stronger resource isolation, use a separate Static Web App resource because preview environments do not support custom domains.
- The current quota page lists 100 GB of included monthly bandwidth for the Free plan. Recheck current quotas before provisioning.

## CI/CD and secret handling

- Run lightweight checks, such as HTML validation and link checking, in GitHub Actions before deploying.
- Keep the Azure deployment credential in GitHub Actions secrets; never commit it to the repository.
- The exact checks and branch protection rules remain to be chosen.

## Open decisions

- Select and register the domain; decide whether the canonical hostname is the apex domain or a `www` subdomain.
- Decide which automated checks must pass before a deployment.
- Confirm the Azure hosting plan and quotas at provisioning time.

## Microsoft Learn references

- [Azure Static Web Apps build configuration](https://learn.microsoft.com/azure/static-web-apps/build-configuration)
- [Branch environments](https://learn.microsoft.com/azure/static-web-apps/branch-environments)
- [Review pull requests in pre-production environments](https://learn.microsoft.com/azure/static-web-apps/review-publish-pull-requests)
- [Preview environments](https://learn.microsoft.com/azure/static-web-apps/preview-environments)
- [Custom domains](https://learn.microsoft.com/azure/static-web-apps/custom-domain)
- [Quotas](https://learn.microsoft.com/azure/static-web-apps/quotas)
- [Hosting plans](https://learn.microsoft.com/azure/static-web-apps/plans)
