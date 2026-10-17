# PDev Tool Hub — Bio Landing Page

Ultra-lightweight (< 5KB), fast (< 50ms), responsive landing page designed for proxy and link bridge forwarding in **Link4m Rotation Tool**.

---

## ⚡ How it works

1. When configured with a self-hosted `bridge_url` in `config.json` (e.g. `https://pdev-hub.pages.dev` or `https://pdev-hub.vercel.app`), the tool base64 encodes the destination Link4m URL and appends it to the URL hash:
   ```
   https://pdev-hub.pages.dev/#aHR0cHM6Ly9saW5rNG0uY29tL3hhYmNkZWY=
   ```
2. On page load, `index.html` parses `window.location.hash`, decodes the base64 URL via `atob()`, and binds it directly to the **"Get Free Access Now"** Call-to-Action button.
3. This creates a legitimate bio referral referrer for Link4m tracking while maintaining high speed and zero backend requirement.

---

## 🚀 Quick Deployment Options

### 1. Cloudflare Pages (Recommended - 100% Free & Global CDN)
1. Log in to [Cloudflare Dashboard](https://dash.cloudflare.com/) > **Workers & Pages**.
2. Click **Create Application** > **Pages** > **Upload Assets**.
3. Create a project name (e.g., `pdev-hub`).
4. Drag and drop the `bio_landing_page/` directory (containing `index.html`).
5. Click **Deploy Site**.
6. Copy the output domain (e.g. `https://pdev-hub.pages.dev`) and paste into `config.json` under `"bridge_url"`.

### 2. Vercel
1. Install Vercel CLI (or connect GitHub):
   ```bash
   npm i -g vercel
   ```
2. In this directory, run:
   ```bash
   cd bio_landing_page
   vercel deploy --prod
   ```
3. Copy your live Vercel domain (e.g. `https://pdev-hub.vercel.app`) into `config.json` under `"bridge_url"`.

### 3. GitHub Pages
1. Push this directory to a GitHub repository.
2. In Repository **Settings** > **Pages**:
   - Source: **Deploy from a branch**.
   - Branch: `main` / folder: `/root` (or `/docs`).
3. Your bridge URL will be: `https://<username>.github.io/<repo-name>/`.
