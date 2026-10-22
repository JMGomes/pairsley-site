# pairsley-site

The website of Pairsley: Memory Match. Three static pages, no build step.

| Path | Purpose |
|---|---|
| `/` | The landing page. |
| `/privacy/` | The privacy policy. Both app stores link to it. |
| `/support/` | The support page. The App Store links to it. |

## Preview

```
python3 -m http.server 8000
```

Open `http://localhost:8000/`.

## Deploy

The site is live at https://pairsley.app/. GitHub Pages serves the `main` branch from the repository root. The `CNAME` file binds the custom domain, and the old address, jmgomes.github.io/pairsley-site, redirects there. `.nojekyll` stops Pages from running Jekyll over the files.

## DNS at the registrar

The domain is registered at GoDaddy. Pages needs these records:

| Type | Name | Value |
|---|---|---|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `jmgomes.github.io` |

Delete the parked A record and the parked `www` record that GoDaddy adds by default.

## To do before launch

1. Add the support email address to the privacy page and the support page.
2. Complete the privacy policy for the released version.
3. Replace "Coming soon" with the App Store and Google Play links.
