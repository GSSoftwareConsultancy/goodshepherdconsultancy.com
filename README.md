# goodshepherdconsultancy.com

The company site for Good Shepherd Software Consultancy Limited (company no. 09702990),
served by GitHub Pages from `main`. One hand-written HTML page, no build step, no framework.

- `index.html` — the page. The product marks are inlined as SVG symbols so the page has no
  dependency on enrichmeai.com.
- `assets/` — the company mark (a shepherd's crook on pasture green), the favicon and the
  PNGs. The mark family is generated in the enrichmeai.com site repo, `assets/brand/`.
- `CNAME` — the custom domain. Merging to `main` publishes.

## Domain and DNS

The domain is registered with Wix and stays there (registration only; the Wix site plan is
not needed). DNS is edited in the Wix domain dashboard. Records that point the domain here:

| Type | Host | Value |
|---|---|---|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| AAAA | `@` | `2606:50c0:8000::153`, `2606:50c0:8001::153`, `2606:50c0:8002::153`, `2606:50c0:8003::153` |
| CNAME | `www` | `gssoftwareconsultancy.github.io` |

Leave the Google Workspace records alone: the five `MX` records on `aspmx.l.google.com` and
the two `TXT` records (`v=spf1 include:_spf.google.com ~all` and `google-site-verification`).
Mail on this domain depends on them.

Once the A records resolve to GitHub, turn on **Enforce HTTPS** in the repository's Pages
settings. GitHub provisions the certificate after DNS propagates, which can take up to a day.

## Checking a change is live

```bash
curl -s https://goodshepherdconsultancy.com/ | grep -o "<title>[^<]*"
```
