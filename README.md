# Redactify.me

Static single-page site for Redactify, a bespoke security consultancy based in Park City, UT.

## Structure

- `index.html` — markup
- `style.css` — styles
- `CNAME` — custom domain for deploys

No build step. No dependencies. Open `index.html` directly or serve the folder with any static file server.

## Local preview

```sh
cd ~/dev/redactify-site
python3 -m http.server 8080
# then open http://localhost:8080
```

## Deploy to Cloudflare Pages

### Option A — Direct Upload (fastest)

1. Go to https://dash.cloudflare.com → Workers & Pages → Create → Pages → **Upload assets**.
2. Name the project `redactify`.
3. Drag the contents of `~/dev/redactify-site/` (not the folder itself) into the upload area.
4. Click **Deploy site**.

### Option B — Git integration

1. Push this directory to a GitHub repo (e.g. `parkerbrand/redactify-site`).
2. Cloudflare dashboard → Workers & Pages → Create → Pages → **Connect to Git**.
3. Select the repo. Framework preset: **None**. Build command: *(leave blank)*. Build output directory: `/`.
4. Save and deploy.

### Custom domain

1. In the Pages project → **Custom domains** → **Set up a custom domain**.
2. Enter `redactify.me`. Cloudflare will auto-provision the DNS record if the zone is on Cloudflare; otherwise add the CNAME it shows you at your registrar.
3. Add `www.redactify.me` as a second custom domain if desired.

The included `CNAME` file is harmless on Cloudflare Pages (it's consumed by GitHub Pages); Cloudflare binds the domain through its dashboard.

## Editing content

All copy lives in `index.html`. All styling lives in `style.css`. Change, save, refresh.
