# Portfolio Preview

A small, intentionally generic static-site placeholder for Phase 1 of the portfolio project. It uses plain HTML and CSS, with no personal or project details, JavaScript, framework, or build step.

## Live preview

The current site is available at [https://happy-island-03fc6e900.4.azurestaticapps.net](https://happy-island-03fc6e900.4.azurestaticapps.net).

This Azure-generated URL is temporary. The README link will be replaced with the final custom domain in Phase 3.

## Run locally

From the repository root, start Python's built-in static web server with `src` as its document root:

```powershell
py -m http.server 8000 --directory src
```

If the `py` launcher is unavailable, use:

```powershell
python -m http.server 8000 --directory src
```

Then open [http://localhost:8000](http://localhost:8000) in a browser. Stop the server with `Ctrl+C`.

## Project files

- `src/index.html` — page structure and placeholder copy.
- `src/styles.css` — layout, visual styles, and responsive rules.
- `docs/` — project plan, architecture, and phase task checklist.

The real portfolio content and design are planned for Phase 2. A custom domain is deferred to Phase 3.
