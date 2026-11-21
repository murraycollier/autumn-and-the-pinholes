# Autumn and the Pinholes

The website for Autumn and the Pinholes, a modern folk band. Built with [Hugo](https://gohugo.io) and hosted on GitHub Pages.

Live site: https://murraycollier.github.io/autumn-and-the-pinholes/

## Running it locally

1. Install Hugo **extended** (v0.170.1 or newer, the version the deploy uses).
2. From this folder, run:

   ```bash
   hugo server -D
   ```

3. Open http://localhost:1313/autumn-and-the-pinholes/

## Where things live

| What you want to change | File |
| --- | --- |
| Site name, tagline, booking email, social links, nav menu, form endpoint | `hugo.toml` |
| Albums, EPs, tracklists, streaming links | `data/music.yaml` |
| Gig dates and venues | `data/shows.yaml` |
| Band members and bios | `data/members.yaml` |
| Gallery photos and captions | `data/gallery.yaml` (images go in `static/images/gallery/`) |
| About page story | `content/about/_index.md` |
| Contact page text | `content/contact/_index.md` |
| Colours, fonts, spacing | `assets/css/main.css` (colours are CSS variables at the top) |
| Menus, homepage, page layouts | `layouts/` |

### Adding a show

Add an entry to `data/shows.yaml`. Dates must be quoted `YYYY-MM-DD` strings. Shows move from "Coming up" to "Already happened" automatically once their date passes.

```yaml
- date: "2027-03-01"
  time: "20:00"
  venue: "The Example Arms"
  city: "Somewhere"
  note: "Support from someone brilliant"
  tickets: "https://example.com/tickets"
```

### Adding a release

Add an entry to `data/music.yaml` with a cover image in `static/images/covers/`. Fill in any streaming links you have; empty links are hidden.

### Contact form

Set `formEndpoint` in `hugo.toml` to a form service endpoint (for example, a Formspree URL). Until then, the contact page shows a plain email button.

## Deploying

Pushing to `main` runs `.github/workflows/hugo.yml`, which builds the site with Hugo and publishes it to GitHub Pages. In the repository settings, Pages must be set to **Source: GitHub Actions**.

If the repository name changes, update `baseURL` in `hugo.toml` to match.
