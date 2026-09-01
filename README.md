# SpinDex AI — Product & Legal Site

Static marketing and legal pages for the **SpinDex AI** app by Generalsoft,
intended for Google Play and Apple App Store publication.

## Pages

| File | Purpose | Required by |
|------|---------|-------------|
| `index.html` | Product / landing page | — |
| `privacy.html` | Privacy Policy | Google Play & App Store |
| `terms.html` | Terms of Service | Recommended (Apple EULA / Play) |
| `support.html` | Support / contact | App Store (support URL) |
| `data-deletion.html` | Data deletion instructions | Google Play (data deletion) |

## Local preview

Open any HTML file directly in a browser, or serve the folder:

```bash
cd ~/src/spindexai/product
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deployment (GitHub Pages, custom domain)

The site is published at **https://spindex.generalsoft.ai/**. The `CNAME` file at
the repo root already contains this value.

1. Push this folder to a GitHub repository (e.g. `generalsoft/spindex-product`).
2. In the repo, go to **Settings → Pages**:
   - Source: **Deploy from a branch**, branch `main`, folder `/ (root)`.
3. Under **Custom domain**, enter `spindex.generalsoft.ai` and **Save**.
4. Configure DNS for `spindex.generalsoft.ai`:
   - Add a `CNAME` record pointing `spindex.generalsoft.ai` → `<username>.github.io`
     (for example `generalsoft.github.io`).
   - Propagation can take from a few minutes to a few hours.
5. Back in **Settings → Pages**, enable **Enforce HTTPS** once the TLS certificate
   has been issued.

The site uses relative links and is served from the domain root, so no base path
or `<base href>` is required.

## URLs to paste into the stores

Use these exact URLs in the store consoles:

| Field | URL |
|-------|-----|
| Marketing / product page | `https://spindex.generalsoft.ai/` |
| Privacy Policy (Google Play) | `https://spindex.generalsoft.ai/privacy.html` |
| Privacy Policy (App Store Connect) | `https://spindex.generalsoft.ai/privacy.html` |
| Support URL (App Store Connect) | `https://spindex.generalsoft.ai/support.html` |
| Support email | `support@spindex.generalsoft.ai` |
| Data deletion (Google Play) | `https://spindex.generalsoft.ai/data-deletion.html` |
| Terms of Service | `https://spindex.generalsoft.ai/terms.html` |

## Before publishing — TODOs

1. **Replace the App Store badge link** in `index.html`. The Apple listing URL
   contains a numeric ID (e.g. `https://apps.apple.com/app/id1234567890`). Search
   `index.html` for `idXXXXXXXXX` and replace it. The Google Play link already uses
   the application ID `com.generalsoft.spindex` and should work once published.
2. **Confirm the support email** is monitored (`support@spindex.generalsoft.ai`).
3. **Review legal wording** — the Privacy Policy and Terms are templates tailored to
   SpinDex AI's actual features. Have them reviewed by counsel before going live, and
   update the "Last updated" dates if you edit them.
4. **Update the company name/domain** if anything differs from "Generalsoft" /
   `generalsoft.ai`.
