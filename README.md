# Open OSINT Monitor – GitHub Pages (No Keys)

This version supports **brand-only scans** (TLD sweep) and **download as JSON/CSV**. It works entirely on GitHub Pages using only free, no-login sources.

## Features
- Brand TLD sweep (e.g., `dell.in`, `dell.ru`, `dell.xyz`, … across ~60 popular TLDs)
- Domain RDAP / WHOIS, DNS (A/AAAA/MX/NS/TXT), SPF/DMARC
- GeoIP/ASN/ISP for first A record (ipwho.is)
- Certificate Transparency (crt.sh) lookalike harvesting
- Subdomains (sonar.omnisint.io)
- Risk badges + progress indicator
- Download JSON/CSV (client-side)

## Publish
Upload the folder contents to a GitHub repo and enable **Settings → Pages → Deploy from a branch**.

## Notes
- Public endpoints impose rate limits; scans of many TLDs take time and may be partial.
- `crt.sh` and some RDAP servers don’t set CORS; the code includes a read-only `r.jina.ai` fallback.
- This is for defensive security. Always verify results before action.
