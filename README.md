# jismy.in — portfolio site

Static single-page site. No build step, no dependencies. Edit `index.html` and push.

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire site — HTML, CSS and JS in one file |
| `CNAME` | Tells GitHub Pages the custom domain is `jismy.in` |
| `robots.txt` | Allows crawling, points to the sitemap |
| `sitemap.xml` | Single-URL sitemap — update `lastmod` when the page changes |
| `assets/` | Images (see below) |

## Images still needed

Drop these into `assets/` using exactly these filenames and the placeholders disappear
(each `<div class="ph">` block in `index.html` is replaced with an `<img>` — see "Swapping in images").

| Filename | Ratio | What it is |
|---|---|---|
| `reel-1.jpg` … `reel-4.jpg` | 9:16 | Thumbnail frames for the organic-growth case study |
| `mibyjismy.jpg` | 16:10 | Screenshot of the MI BY JISMY homepage |
| `ads-dashboard.jpg` | 16:10 | Screenshot of a Google Ads or Meta Ads dashboard |
| `insights.jpg` | 16:10 | Screenshot of the Instagram Insights reach panel |
| `hay.png`, `almarah.png`, `iha.png`, `twinbirds.png` | square | Brand logos — check permission first |
| `og-image.jpg` | 1200×630 | Social share preview |
| `favicon.png` | 512×512 | Browser tab icon |
| `jismy-thomas-resume.pdf` | — | Downloadable résumé |

Export images at roughly 2× their display size, then compress at squoosh.app.
Aim for under 200 KB each — page speed is a ranking factor and it is one
of the things this site is meant to demonstrate.

### Swapping in images

Replace a placeholder like this:

```html
<div class="reel-frame"><div class="ph">THUMBNAIL<br>assets/reel-1.jpg</div><span class="play"></span></div>
```

with:

```html
<div class="reel-frame"><img src="assets/reel-1.jpg" alt="Styling reel — co-ord set" style="width:100%;height:100%;object-fit:cover"><span class="play"></span></div>
```

Always write a real `alt` description. It matters for accessibility and for image search.

## Text still to fill in

- Confirm the creator start date in the timeline (currently "2026")
- Decide whether to name the client-campaign deliverables individually

## Deploying to GitHub Pages

1. Create a public repo — any name works, e.g. `jismy-site`.
2. Upload these files to the repo root (drag and drop works: **Add file → Upload files**).
3. **Settings → Pages → Build and deployment**: Source = *Deploy from a branch*, Branch = `main`, folder = `/ (root)`.
4. In the same Pages screen, set **Custom domain** to `jismy.in` and save. Add the domain in GitHub *before* changing DNS.
5. At the domain registrar's DNS panel, add four A records for the apex domain pointing to GitHub's Pages IPs:
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   (and optionally the matching AAAA records for IPv6). Add a CNAME record for `www` pointing to `<username>.github.io`.
6. Wait for DNS to propagate — up to 24 hours, usually much less — then tick **Enforce HTTPS** in the Pages settings.

Source: GitHub Pages documentation, "Managing a custom domain for your GitHub Pages site".
Verify the IPs there before entering them, in case they have changed.

## After launch

- Verify the site in **Google Search Console** and submit `sitemap.xml`.
- Add **Google Analytics** if you want traffic data — it is also one more tool demonstrated in public.
- Put `jismy.in` in the Instagram bio link slot. There were 8,512 profile visits in 30 days with no link there.
- Re-check the stats in the hero band every few months. They are hard-coded in `index.html`
  under `<!-- ============ STATS ============ -->`.

## Adding a blog later

Add a `/blog/` folder with one HTML file per post, and add each URL to `sitemap.xml`.
If posting becomes regular, move to a static site generator (Astro, Eleventy) rather than
hand-writing each page.
