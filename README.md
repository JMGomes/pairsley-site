# pairsley-site

The website of Pairsley: Memory Match. Three static pages, no build step. Light theme only, like the app. The Nunito font is served from `assets/fonts` (OFL licence), so the pages load nothing from other sites.

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

1. Complete the privacy policy for the released version.
2. Replace "Coming soon" with the official App Store and Google Play badges and links.

## Search engines (follow-up)

Do these steps once. They tell Google and Bing about the site.

1. Open [Google Search Console](https://search.google.com/search-console).
2. Add `pairsley.app` as a **Domain** property.
3. Copy the TXT record that Google shows.
4. In GoDaddy DNS, add the TXT record for the name `@`. Then click **Verify** in Search Console. DNS changes can take up to an hour.
5. In Search Console, open **Sitemaps** and submit `https://pairsley.app/sitemap.xml`.
6. Open [Bing Webmaster Tools](https://www.bing.com/webmasters) and choose **Import from Google Search Console**. Bing also supplies DuckDuckGo and Yahoo.

## When the apps are live

1. Add the App Store and Google Play links to `sameAs` in the structured data of `index.html`.
2. Add the Smart App Banner: `<meta name="apple-itunes-app" content="app-id=APP_STORE_ID">`.
3. Update `lastmod` in `sitemap.xml` after each content change.
