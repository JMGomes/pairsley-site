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

GitHub Pages serves the `main` branch from the repository root at https://jmgomes.github.io/pairsley-site/. `.nojekyll` stops Pages from running Jekyll over the files. All links are relative, so the pages also work under a custom domain.

## To do before launch

1. Add the support email address to the privacy page and the support page.
2. Complete the privacy policy for the released version.
3. Replace "Coming soon" with the App Store and Google Play links.
4. Add a custom domain: a `CNAME` file, the DNS records at the registrar, and a `sitemap.xml` and `robots.txt` with the full URLs.
