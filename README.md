# CV — Pat Reen

Web-format CV built with Jekyll, deployed via GitHub Pages.

## Local development

Requires [Docker Desktop](https://www.docker.com/products/docker-desktop/).

```bash
docker compose up
```

Then open:
- `http://localhost:4000` — web view
- `http://localhost:4000/print` — print/PDF view

Jekyll watches for file changes and rebuilds automatically. Stop with `Ctrl+C`.

## Updating content

All CV content lives in a single file: `_data/data.yml`

| Section | Key |
|---------|-----|
| Name, tagline, contact links | `sidebar` |
| Overview paragraph | `career-profile.summary` |
| Skills (grouped tags) | `skills.groups` |
| Work history | `experiences` |
| Education | `education` |
| Industry contributions | `projects` |

## Generating the PDF

1. Run locally (see above) or push to GitHub Pages
2. Go to [webtopdf.com](https://webtopdf.com/) and convert the `/print` URL to PDF
3. Save the output as `assets/images/pat-reen-CV-print.pdf`
4. Commit the updated PDF

## Structure

```
_data/data.yml          # All CV content (edit this)
_includes/              # HTML components (sidebar, experiences, skills, etc.)
_layouts/               # Page layouts (default = web, print = PDF view)
_sass/                  # Stylesheets
  _base.scss            # Core styles
  _print.scss           # Print media overrides
  skins/                # Colour themes (set in _config.yml → theme_skin)
assets/images/          # Profile photo + generated PDF
```

## Credits

Template: [sharu725/online-cv](https://github.com/sharu725/online-cv)
