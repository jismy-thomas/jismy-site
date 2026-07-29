# jismy.in

Personal portfolio site for Jismy Thomas, digital marketer.
Live at **[jismy.in](https://jismy.in)**.

Static single-page site: hand-written HTML and CSS, no framework, no build step,
no dependencies. Edit `index.html`, commit, and the change is live within a minute.

## Structure

| File | Purpose |
|---|---|
| `index.html` | The entire site. HTML, CSS and JavaScript in one file. |
| `assets/` | Images, logos and the résumé PDF |
| `CNAME` | Custom domain for GitHub Pages |
| `robots.txt` | Crawl rules, points to the sitemap |
| `sitemap.xml` | Sitemap submitted to Google Search Console |

Sections, in order: hero, headline stats, capabilities, three case studies,
client campaigns, toolkit, experience timeline, contact.

## Editing

Everything lives in `index.html`. The CSS is in a single `<style>` block at the top;
colours are defined as custom properties on `:root`, so the whole palette can be
changed from about six lines.

```css
--paper   /* page background */
--ink     /* body text */
--blue    /* links, buttons, accents */
--deep    /* dark section backgrounds */
--amber   /* small highlights */
```

Section headings are marked with HTML comments (`<!-- CAPABILITIES -->`) to make
them easy to find.

### Replacing an image

Keep the same filename in `assets/` and nothing else needs changing. If adding a new
one, follow the existing pattern and always write a real `alt` description:

```html
<img src="assets/example.jpg" alt="What the image actually shows"
     style="width:100%;height:100%;object-fit:cover">
```

Export at roughly 2× display size and compress before committing. Page speed matters
here, both for visitors and because a marketing portfolio ought to practise what it
describes.

## Deployment

GitHub Pages, deploying from `main` at the repository root. Pushing to `main` publishes.

The custom domain is configured through `CNAME` plus four A records at the registrar
pointing to GitHub's Pages IP addresses, with a CNAME record on `www`. See GitHub's
documentation on managing a custom domain for the current values.

## Analytics

Google Analytics 4 is loaded in the `<head>`. Alongside standard pageviews, the script
at the foot of the page fires custom events for contact-link clicks, résumé downloads,
outbound social clicks and reel clicks, so the site can be judged on whether people
actually reach the contact section rather than on raw traffic.

## Housekeeping

The Instagram figures shown in the stats band and the organic-growth case study are a
90-day snapshot with the date stated on the page. When they are refreshed, three places
need updating together, or they will disagree with each other:

1. The stats band near the top
2. The KPI block in the organic-growth case study
3. `assets/insights.jpg`

Update `lastmod` in `sitemap.xml` after any substantial change.

---

Built in 2026.
