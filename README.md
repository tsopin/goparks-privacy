Privacy Policy Site — Deployment Guide
====================================

Pick one of these zero-cost hosting options. Point a subdomain like `privacy.yourdomain.com` from Namecheap.

Option A — GitHub Pages (simple, free)
-------------------------------------
1) Create a new public repo on GitHub (e.g., `privacy-site`).
2) Copy the contents of `privacy-site/` (this folder) into the repo root. Commit and push.
3) In GitHub: Settings → Pages → Build and deployment → Source: `Deploy from a branch`, Branch: `main` (`/root`). Save.
4) Wait ~1 minute. Your site will be live at `https://<your-username>.github.io/<repo>`.
5) Custom domain:
   - Settings → Pages → Custom domain: enter `privacy.yourdomain.com`.
   - Ensure repo contains a `CNAME` file with exactly `privacy.yourdomain.com`.

Namecheap DNS for GitHub Pages (subdomain)
- Domain List → Manage → Advanced DNS → Add new record:
  - Type: CNAME Record
  - Host: `privacy`
  - Value: `<your-username>.github.io`
  - TTL: Automatic
- Wait for DNS propagation (usually minutes, up to 24h).

Option B — Netlify (free tier, very easy)
----------------------------------------
1) Push this folder to a new repo (public or private).
2) Netlify → New site from Git → pick your repo.
3) Build command: none. Publish directory: `/` (repo root containing index.html).
4) Deploy. You’ll get `https://<random>.netlify.app`.
5) Add custom domain: Site settings → Domain management → Add domain: `privacy.yourdomain.com`.
6) Namecheap DNS: create a CNAME record
   - Host: `privacy`
   - Value: `<your-site>.netlify.app`
   - TTL: Automatic

Edit This Policy
----------------
- In `index.html`, replace:
  - `Your Company Name` with your legal entity/app name
  - `privacy@yourdomain.com` with your contact email
  - Update the Last updated date

Quick Publish Checklist
-----------------------
- [ ] Decide host: GitHub Pages or Netlify
- [ ] Replace placeholders in `index.html`
- [ ] Choose subdomain: e.g., `privacy.yourdomain.com`
- [ ] Set Namecheap DNS CNAME for `privacy` to your host target
- [ ] If GitHub Pages: ensure `CNAME` file matches your subdomain
- [ ] Verify HTTPS loads at your subdomain (may need up to 24h for DNS)

Optional
--------
- Add `robots.txt` if you want search engines to index the page
- Keep repo private with Netlify if you don’t want the policy’s source public
