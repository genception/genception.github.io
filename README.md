# Project Page

Self-contained project page for the paper. Everything lives in `index.html` (HTML + inline CSS/JS), so there is no build step.

## Preview locally

Just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Deploy as a GitHub organization page (like the reference site)

This page is set up to deploy to **https://genception.github.io/** — served from a repo named exactly `genception.github.io` inside a GitHub org named `genception`.

1. **Create a GitHub organization** named `genception` (if you don't have it): https://github.com/organizations/plan → Free plan → org name `genception`.
2. **Create a repository** in that org named `genception.github.io` (must match the org name + `.github.io`). Leave it empty (no README).
3. **Push this folder** to the repo's default branch (`main`):
   ```bash
   cd website
   git init
   git add .
   git commit -m "Initial project page"
   git branch -M main
   git remote add origin https://github.com/genception/genception.github.io.git
   git push -u origin main
   ```
4. **Pages is deployed via GitHub Actions** (repo → Settings → Pages → Source = "GitHub Actions"). The workflow at `.github/workflows/deploy.yml` publishes the site on every push to `main` — no Jekyll build (a `.nojekyll` file disables it). Watch runs under the repo's **Actions** tab.
5. Wait for the deploy run to finish (~1 minute), then visit **https://genception.github.io/**.

> Note: this repo is currently **public** (GitHub Pages requires a public repo on the Free plan). The page is intentionally anonymized while under review.

> Alternative (personal user page): put this in a repo under your own account named `<username>.github.io`, served at `https://<username>.github.io/`. Or any repo with Pages enabled, served at `https://<username>.github.io/<repo>/`.

## Adding media

Create an `assets/` folder next to `index.html` and reference files relatively, e.g. `assets/overview.mp4` or `assets/method.png`. Replace the `.video-placeholder` blocks in `index.html` with real `<video>` / `<img>` tags — search the file for `TODO` and `coming soon`.

Large videos are better hosted externally (e.g. cloud storage or YouTube) to keep the repo small.

## What to fill in

Search `index.html` for `TODO` — title, authors, affiliations, links, abstract, method, results, and BibTeX are all marked.
