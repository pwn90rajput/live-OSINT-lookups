# Open OSINT Monitor (GitHub Pages, no keys)

A static website that performs live OSINT checks for any domain using **only free, no‑login APIs** that support CORS, so it can run entirely in the browser on **GitHub Pages**.

### What it shows
- **WHOIS/RDAP**: registrar, registration dates, status, privacy/proxy
- **DNS**: A/AAAA/MX/NS/TXT, SPF, DMARC presence (via DNS‑over‑HTTPS)
- **IP Geo/ASN/ISP**: for the first few A records (ipwho.is)
- **Certificate Transparency** lookups via crt.sh
- **Subdomains** via sonar.omnisint.io
- **Risk badges**: quick heuristic scoring (no ML keys required)

> Note: All calls are client‑side. Some providers may rate‑limit or change CORS behaviour.

### Quick start (GitHub Pages)
1. Create a new repo, upload this folder (files inside, not a ZIP).
2. In **Settings → Pages**, select **Deploy from a branch**, choose your default branch and **/root**.
3. Open the Pages URL and search for any domain.

### No server / no keys
- DNS: Cloudflare DoH (`cloudflare-dns.com`) and Google DoH (`dns.google`) – both allow CORS for JSON.
- RDAP: `rdap.org` (with a CORS fallback through `r.jina.ai` content mirror).
- GeoIP: `ipwho.is` allows CORS.
- CT: `crt.sh` does not provide CORS; we read JSON through `r.jina.ai` (best‑effort).
- Subdomains: `sonar.omnisint.io` (community endpoint; may be rate‑limited). Fallback via `r.jina.ai`.

### Legal/Ethical
This tool is for **defensive security** and monitoring of domains you own or have permission to assess. Respect rate limits and terms of use.

### Customize
- Add columns in `assets/app.js` (rendering functions).
- Style in `assets/styles.css`.
- If you later want PDF exports or persistence/history, add a backend (Render/Worker) or GitHub Actions workflow to commit JSON snapshots.
