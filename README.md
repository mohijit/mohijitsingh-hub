# mohijitsingh-hub

Static landing page at `mohijitsingh.com`, hosted on GitHub Pages. Links out to each
project's own subdomain — this repo owns only the root domain, nothing else.

## Adding a new project subdomain

Each project gets its own repo, own host, own subdomain, own `PUBLIC_BASE_URL` (or
equivalent). Nothing here couples their deploys together.

1. Deploy the project wherever it lives (Railway, GitHub Pages, etc.) as normal.
2. In that host's dashboard, add a custom domain: `<name>.mohijitsingh.com`.
3. The host will show you a DNS record to add (usually a CNAME). Add it in Wix's
   **Domains → mohijitsingh.com → Advanced DNS Settings** — Wix is the authoritative
   nameserver for this domain (`ns12/13.wixdns.net`), not a separate registrar.
4. Add a card for it in `index.html` here, pointing at the new subdomain.

## DNS

DNS is managed in Wix's dashboard (Domains → mohijitsingh.com → Advanced DNS Settings),
even though nothing is actually hosted on Wix — the domain's nameservers point there.

Records this repo needs at the apex (`@`):

| Type | Host | Value |
|------|------|-------|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

These are GitHub Pages' standard apex-domain IPs (fixed, documented, not repo-specific).
