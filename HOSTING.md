# Hosting

## Now
- GitHub Pages: https://jukiyak.github.io/helm-field-notes/
- Repo: https://github.com/jukiyak/helm-field-notes

## Custom domain on jukiyakinjo.com (Cloudflare DNS already)

`jukiyakinjo.com` NS is Cloudflare; apex/www currently point at Vercel.
Prefer a **subdomain** so Vercel site stays put:

Suggested: `helm.jukiyakinjo.com` → GitHub Pages

1. Cloudflare DNS (jukiyakinjo.com zone):
   - Type: CNAME
   - Name: `helm`
   - Target: `jukiyak.github.io`
   - Proxy: DNS only (grey cloud) while verifying, then can orange-cloud later
2. GitHub repo Settings → Pages → Custom domain: `helm.jukiyakinjo.com`
3. Wait for HTTPS certificate

### Cloudflare Pages alternative (later)
- `npx wrangler login` on mini
- `npx wrangler pages project create helm-field-notes`
- `npx wrangler pages deploy . --project-name=helm-field-notes`
- Attach custom domain in CF dashboard (same subdomain)

### Mac mini alternative
- Serve static dir behind Tailscale Serve / Funnel, or Caddy + cloudflared tunnel
- Good for private drafts; public field notes better on Pages/CF

## Personal diagrams (2026-09-24)

- Temporary: α/β axes note on this public Pages site (`alpha-beta-axes.html`).
- Target later: private notes host on `app.jukiyakinjo.com` (name may change; do not hard-depend on `helm.`).
- Public Pages is a stopgap only — move private diagrams off when app.* exists.
