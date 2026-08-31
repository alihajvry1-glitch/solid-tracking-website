# Solid Tracking — Website

A single self-contained `index.html` (no build step, no dependencies). Open it locally by double-clicking, or deploy it anywhere.

---

## Option A — GitHub Pages (auto-deploys on every push) ✅ recommended

1. Create a new repository on GitHub (e.g. `solid-tracking-website`).
2. Upload **everything in this folder** (keep `index.html` at the repo root and the `.github/` folder as-is).
   - Web upload: repo → **Add file → Upload files** → drag the contents in → **Commit**.
   - Or with git:
     ```bash
     git init && git add . && git commit -m "Solid Tracking website"
     git branch -M main
     git remote add origin https://github.com/<you>/<repo>.git
     git push -u origin main
     ```
3. In the repo: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
4. Done. Every push to `main` auto-publishes. Your site: `https://<you>.github.io/<repo>/`.

## Option B — Netlify / Vercel / Cloudflare Pages (drag & drop)

- **Netlify:** https://app.netlify.com/drop → drag `index.html` (or this folder). Instant live URL.
- **Vercel / Cloudflare Pages:** New Project → import the GitHub repo (or upload). Framework preset: **None / Static**. Output/root: the folder containing `index.html`.
- Connecting the GitHub repo makes these auto-deploy on every push too.

---

## Add your custom domain

1. Buy a domain (Cloudflare, Namecheap, GoDaddy; `.sa` via a SaudiNIC registrar).
2. In your host's dashboard → **Domains / Custom domain** → add your domain.
3. Add the DNS records the host shows you at your registrar:
   - Root domain (`solidtracking.sa`): an `A` record (or `ALIAS`/`CNAME` flattening) to the host.
   - `www`: a `CNAME` to the host's target.
   - **GitHub Pages:** add a file named `CNAME` at the repo root containing just your domain (e.g. `solidtracking.sa`), then set the domain under Settings → Pages.
4. HTTPS/SSL is issued automatically. Propagation: minutes to a few hours.

---

## Editing the site

This `index.html` is a compiled bundle — **don't edit it by hand.** To make changes, update the source design (`Solid Tracking.dc.html`) in the design tool, re-export the standalone file, and replace `index.html` here. Then push (or re-drag) to redeploy.
