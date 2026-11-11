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

## App store links

The iPhone app is live on the App Store (app ID `6825919047`). The landing page shows Apple's official badge from `assets/badges/app-store.svg`. The badge links to the App Store. Safari on iPhone also shows the Smart App Banner.

## Search engines (follow-up)

Do these steps once. They tell Google and Bing about the site.

1. Open [Google Search Console](https://search.google.com/search-console).
2. Add `pairsley.app` as a **Domain** property.
3. Copy the TXT record that Google shows.
4. In GoDaddy DNS, add the TXT record for the name `@`. Then click **Verify** in Search Console. DNS changes can take up to an hour.
5. In Search Console, open **Sitemaps** and submit `https://pairsley.app/sitemap.xml`.
6. Open [Bing Webmaster Tools](https://www.bing.com/webmasters) and choose **Import from Google Search Console**. Bing also supplies DuckDuckGo and Yahoo.

## When the Android app is live

1. Get the official "Get it on Google Play" badge from Google's badge page and save it in `assets/badges/`.
2. Add the badge next to the App Store badge in the hero and in the closing panel of `index.html`.
3. Replace "Free on iPhone. Android is coming soon." with a sentence about both phones.
4. Add the Google Play link to `sameAs` and set `operatingSystem` to `iOS, Android` in the structured data of `index.html`.
5. Update `lastmod` in `sitemap.xml`. Do this after each content change.
