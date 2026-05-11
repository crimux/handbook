# DEPLOY.md — Cloudflare Pages click-path for crimux.com

This is the exact path to get the repo live at `https://crimux.com` and `https://www.crimux.com`, with `www → apex` redirect.

## Prerequisites

- The Cloudflare account that owns `crimux.com` (already done).
- Admin on the GitHub org `crimux` (already done).
- The repo pushed to `github.com/crimux/crimux` (use the one-line push command from this `README` after unzipping).

## 1. Create the Pages project

1. Cloudflare dashboard → **Workers & Pages** → **Create application** → **Pages** → **Connect to Git**.
2. Authorize Cloudflare's GitHub app for the `crimux` org if not already; pick repository `crimux/crimux`.
3. Production branch: `main`.
4. Build settings:
   - **Framework preset:** *Astro*
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
   - **Root directory:** `/` (leave default)
   - **Node version:** `20` (Settings → Environment variables → `NODE_VERSION=20`)
5. **Save and Deploy.**

The first deploy lands at `https://crimux.pages.dev`. Confirm it renders, then proceed.

## 2. Custom domains

In the Pages project → **Custom domains** → **Set up a custom domain**.

1. Add `crimux.com` (apex).
   - Cloudflare proposes a CNAME-flattened record automatically since DNS is on the same account. Approve.
2. Add `www.crimux.com`.
   - Approve the CNAME to `crimux.pages.dev`.
3. SSL certificates: issued automatically (Universal SSL + Pages-managed cert). Wait ~5 minutes; status should turn green for both hostnames.

## 3. Redirect `www → apex`

There are two equivalent ways. Pick **one**.

### Option A (recommended): Cloudflare Bulk Redirect

1. Cloudflare dashboard → **Rules** → **Redirect Rules** → **Create rule**.
2. Name: `crimux-www-to-apex`.
3. When incoming requests match: *Hostname* equals `www.crimux.com`.
4. Then: **Static redirect**
   - Type: **301 (Permanent)**
   - URL redirect: `https://crimux.com${http.request.uri}`
   - Preserve query string: **on**
5. Deploy.

### Option B: a Page Rule

1. **Rules** → **Page Rules** → **Create Page Rule**.
2. URL match: `www.crimux.com/*`
3. Setting: **Forwarding URL** → **301** → `https://crimux.com/$1`
4. Save.

Verify: `curl -I https://www.crimux.com` returns `301` with `Location: https://crimux.com/`.

## 4. Cloudflare Web Analytics (optional but recommended)

1. Cloudflare dashboard → **Analytics & Logs** → **Web Analytics** → **Add a site**.
2. Enter `crimux.com`. Copy the issued token (the value inside `data-cf-beacon='{"token":"…"}'`).
3. In this repo, edit `src/layouts/Base.astro` and uncomment the Cloudflare Web Analytics `<script>` tag, replacing `REPLACE_ME` with the token.
4. Commit, push, redeploy.

No third-party trackers are used. No external fonts are loaded.

## 5. Verify the deploy

- Open `https://crimux.com/` — home page renders.
- Open `https://www.crimux.com/` — 301 redirects to the apex.
- Open `https://crimux.com/sitemap-index.xml` — exists and references each page.
- Open `https://crimux.com/robots.txt` — points to the sitemap.
- Run Lighthouse on `/` and `/bibliography` — Performance, Accessibility, Best Practices, SEO all ≥ 95.

## 6. Re-deploys

Every push to `main` triggers a build. Preview deploys are auto-created for every other branch and PR; their URLs appear in the Pages project's *Deployments* tab.

## Troubleshooting

- **Build fails on Node engine warning:** Confirm `NODE_VERSION=20` env var is set in the Pages project.
- **404 on a real page:** Confirm `dist/` contains the route after `npm run build` locally. Astro generates one HTML file per route.
- **`www` doesn't redirect:** The Bulk Redirect / Page Rule has to be on the same Cloudflare zone as the DNS. Check that `crimux.com` is in the correct account.
- **Fonts look wrong on first paint:** Self-hosted via `@fontsource/*`; they're bundled and emitted from `dist/_astro/`. If they 404 in production, confirm the Pages build output includes the `_astro/` directory.
