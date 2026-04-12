# CV — Pat Reen

Web-format CV built with Jekyll, deployed via GitHub Pages.

## Local development

Requires Ruby ([rubyinstaller.org](https://rubyinstaller.org/downloads/) on Windows — download the **Ruby+Devkit** version).

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

Then open:
- `http://localhost:4000` — web view
- `http://localhost:4000/print` — print/PDF view (auto-triggers browser print dialog)

## Updating content

All CV content lives in a single file: `_data/data.yml`

| Section | Key |
|---------|-----|
| Name, tagline, contact links | `sidebar` |
| Encoded contact details (email + phone) | `sidebar.contact_email_enc` / `sidebar.contact_phone_enc` |
| Overview paragraph | `career-profile.summary` |
| Skills (grouped tags) | `skills.groups` |
| Work history | `experiences` |
| Education | `education` |
| Industry contributions | `projects` |

### Updating encoded contact details

Contact details are base64-encoded to keep them off search engine crawls.
To generate a new encoded value:

```bash
python -c "import base64; print(base64.b64encode(b'your value here').decode())"
```

Paste the output into `sidebar.contact_email_enc` or `sidebar.contact_phone_enc` in `data.yml`.

## Generating the PDF

The "Print / Save PDF" button in the sidebar opens `/print`, which automatically triggers the browser print dialog. Use **Save as PDF** as the destination.

## Structure

```
_data/data.yml          # All CV content (edit this)
_includes/              # HTML components (sidebar, experiences, skills, etc.)
_layouts/               # Page layouts (default = web, print = PDF view)
_sass/
  _base.scss            # Core styles
  _print.scss           # Print media overrides
  _responsive.scss      # Responsive breakpoints
  skins/                # Colour themes (set via theme_skin in _config.yml)
assets/images/          # Profile photo, preview image (PNG + SVG source)
```

## Credits

Template: [sharu725/online-cv](https://github.com/sharu725/online-cv)
