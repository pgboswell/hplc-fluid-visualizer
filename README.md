# HPLC Fluid Visualizer

A browser-based HPLC plumbing editor with pumps, valves, columns, detectors, tubing, six example layouts, and calculations for backpressure, band broadening, and gradient delay.

This repository contains only HPLC Fluid Visualizer and the shared styling needed to run it. The other application, full website, contact service, old website backup, screenshots, and private configuration are not included.

## Run locally

The built application is in `public/`. No Java, package installation, or build step is required to run it. Serve it locally with Python:

```
python -m http.server 8000 --directory public
```

Then open http://localhost:8000/.

## Edit and build

- `public/assets/fluid/`: application source, data, and styles.
- `fluid/workspace.html`: application page template.
- `public/assets/site.css`: shared page styles.
- `build.py`: generates `public/index.html` and asset cache versions.

After editing, run:

```
python build.py
```

The build uses Python's standard library and has no dependencies on the original Eclipse workspaces or the full website. The generated HTML is committed for immediate use.

## Tests

Run from the repository root with Node.js:

```
node tests/fluid-model.test.cjs
node tests/fluid-flow.test.cjs
```

The reference fixtures are included. Tests do not require Java or external services. Numerical agreement with the original model is not validation against experimental measurements.

## Hosting

Deploy the `public` directory to a static web host. For Cloudflare Pages, use `python build.py` as the build command and `public` as the output directory. This application has no server-side functions.

## License and attribution

The original software license, CC BY-NC-SA 3.0 US, is retained. See `LICENSE` and `NOTICE`.
