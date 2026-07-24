# Taskfly landing site

Static site for [Taskfly](https://github.com/b-mian/taskfly) — no build step, no dependencies.

## Before publishing

1. In `index.html`, edit the `CONFIG` block at the bottom:
   - `github`: your `owner/repo`
   - `kofi`: your Ko-fi page URL (create one at ko-fi.com, takes 5 minutes).
     The Ko-fi button stays hidden until this is set.
   - `sponsors`: your GitHub Sponsors URL (enable in GitHub → Settings → Sponsors),
     or `null` to hide that button too.
   - After your first release, set `macAsset` / `winAsset` to the exact asset filenames
     so the buttons download directly instead of opening the releases page.
2. In `privacy.html`, keep the `gh` constant in sync.
3. Optional: add screenshots (light + dark) to the hero section.

## Deploy on GitHub Pages

Option A — dedicated site repo:

```bash
cd taskfly-site
git init && git add -A && git commit -m "Taskfly landing site"
gh repo create taskfly-site --public --source . --push
```

Then: repo → Settings → Pages → Source: "Deploy from a branch" → `main` / `/ (root)`.
Site appears at `https://<user>.github.io/taskfly-site/`.

Option B — inside the app repo: copy these files into a `docs/` folder and select
`main` / `/docs` in the Pages settings.

Custom domain (optional): add a `CNAME` file containing your domain and set the DNS
`CNAME` record to `<user>.github.io`.

The `.nojekyll` file tells Pages to serve files as-is.
