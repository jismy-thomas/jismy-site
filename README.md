# jismy.in - portfolio site

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


