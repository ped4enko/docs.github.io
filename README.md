docs.dbn.co.ua
================

This repository contains the statically generated version of **docs.dbn.co.ua**, an archive of Ukrainian construction norms (ДБН, ДСТУ, СНиП, and related reference materials). The site is served directly from GitHub Pages, so every commit to `master` automatically deploys to production.

## Project Structure

- `index.html` – landing page with basic information about the archive.
- `*.html` – individual document pages; each file is already rendered HTML.
- `sitemap-popular.xml` – sitemap that lists the most visited 421 pages from `Страницы.csv`.
- `sitemap-pages-XX.xml` – chunked sitemaps covering the rest of the pages (created in batches of 300 URLs).
- `sitemap.xml` – sitemap index that references all sitemap files.
- `Страницы.csv` – export from analytics containing the popular URLs and their metrics.

## Local Workflow

1. Clone the repo and make changes directly to the HTML files or static assets.
2. Regenerate sitemaps when new pages are added by running the helper script (see `scripts/` if present, otherwise run the ad-hoc Python snippet used previously).
3. Commit changes to `master`; GitHub Pages will deploy automatically.

## Updating Sitemaps

When new documents are added:

1. Update `Страницы.csv` if you want the popular sitemap to reflect fresh analytics.
2. Run the sitemap generation script to refresh `sitemap-popular.xml`, `sitemap-pages-*.xml`, and `sitemap.xml`.
3. Verify the XML formatting (UTF-8, LF endings) and submit the sitemap index to search consoles if needed.

## Support

For questions about the content or to submit corrections, contact `admin@dbn.co.ua`.
