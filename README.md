# Marek Jankola — academic website

A small, readable Jekyll site hosted on GitHub Pages. The original Academic Pages
framework is retained; a dedicated profile layout gives this site its appearance.

## Where to edit

| What you want to change | File |
| --- | --- |
| Biography and homepage section headings | `_pages/about.md` |
| Photo, caption, email, social links, research interests | `_data/profile.yml` |
| Publications and their expandable abstracts | One Markdown file per paper in `_publications/` |
| CV | `_pages/cv.md` |
| Colours, fonts, spacing and mobile layout | `assets/css/profile.css` |
| Page structure and metadata | `_layouts/profile.html` |
| Browser title, description and site settings | `_config.yml` |

For everyday updates, edit a file on GitHub using the pencil button, then choose
**Commit changes**. Every commit to `master` rebuilds and
publishes the website. Your content is rendered into HTML, so visitors can read
it without JavaScript. The Abstract controls use native HTML `details` elements.

## GitHub Pages

The website is deployed at **https://marekjankola.github.io/**.
The repository is **`MarekJankola/marekjankola.github.io`** and Pages uses the
**GitHub Actions** source. Every commit to `master` runs **Build and publish
website**. Check its build and deploy jobs in **Actions** if an update is not
visible yet.

To publish the current version manually:

1. Open **Actions → Build and publish website** in the workflow list.
2. Click **Run workflow**, select **master**, and click **Run workflow** again.
3. Wait for the build and deploy jobs to succeed.

**Re-run jobs** on an existing run repeats that run's original commit. Re-running
an older successful run can therefore replace a newer published website with an
older version. Use **Run workflow → master** to publish the current files.

The deployment now checks that its commit still matches `master` and refuses
to publish if it is outdated. Runs created before this check was added retain
their old workflow, so use a fresh run from `master` instead of re-running them.

The workflow calculates the base path from the repository name. The current
user-site repository publishes at the root address, with no extra path.

## Add a publication

Create `_publications/YYYY-short-title.md`. Copy the existing paper as a guide:

```yaml
---
title: "Your paper title"
date: YYYY-MM-DD
authors: "**Marek Jankola**, Coauthor One, and Coauthor Two"
venue: "Journal or conference"
citation_detail: "Volume, article number"
paperurl: https://arxiv.org/abs/YOUR-ID
arxiv: https://arxiv.org/abs/YOUR-ID
doi: YOUR-DOI
# code: https://github.com/USER/REPOSITORY
# pdf: https://example.org/your-paper.pdf
---

Paste the abstract here. Ordinary Markdown is supported.
```

Use the actual publication date (or the preprint date for a preprint). Files are
listed newest first. Omit optional links that do not exist. Add Markdown emphasis
with `*italics*` or `**bold**`; use Unicode symbols for simple inline mathematics.
The current layout does not load a TeX renderer. If you later write mathematical
blog posts, MathJax or KaTeX can be added to that layout explicitly.

The homepage and CV share this same publication list, so you only edit each paper
once. Preprint and journal versions of the same work belong in one entry.

Theses use the same folder and appear in the same list. Put the degree and
institution in `venue`, link the university record with `paperurl`, and link
the full text with `pdf`. Omit either link when it is not yet available.
For a description that is a summary rather than the original abstract, add
`description_label: Summary`. Remove that field after pasting the original
abstract. If only a thesis year is known, January 1 can be used as a sorting
key in `date`; the website displays only the year.

## Photo and CV

To adjust “Poetic Naturalist.”, edit `--tagline-size` and `--tagline-color` near
the top of `assets/css/profile.css`. The current values are `1.05rem` and
`#5e7287`; smaller font sizes make it smaller, and lighter colours make it
fainter. Mobile screens use 94% of that font size automatically.

In the same stylesheet, `.biography` justifies the introductory paragraphs,
`.research-interests` centres each wrapped row, `h2` sets section headings, and
`.publication h3` sets publication titles.

- `me_photo.jpg` is the original supplied image (4005 × 3816 pixels). The site
  preserves its aspect ratio with `width: 100%; height: auto`; no face editing or
  permanent crop is applied. Replacing it with another file at the same path
  updates the photo. If its proportions change, update the width/height attributes
  in `_includes/profile-sidebar.html` to prevent layout shift.
- The CV link opens `_pages/cv.md`, a concise public academic CV assembled from
  the supplied academic details. The older application PDFs are not included.
  The page has print styling, so a browser's **Print → Save as PDF** works too.
- To use a finished PDF later, add it under `assets/documents/cv.pdf`, and set
  `cv: /assets/documents/cv.pdf` in `_data/profile.yml`.

## Preview locally

Install Ruby and Bundler, then run from the repository directory:

```bash
bundle install
bundle exec jekyll serve --livereload
```

Open the local address printed by Jekyll. Restart after editing `_config.yml`.
You do not need Node or npm for this normal Jekyll editing workflow.

An optional dependency-free Node server is included for checking an already
built site (and for the initial automated visual review):

```bash
bundle exec jekyll build --strict_front_matter
npm run dev
```

It serves only `_site/`, never the raw repository. Rebuild and refresh after
changes. `_site/` is generated output and is not committed.

## Design and provenance

- Warm grey background; dark blue headings; muted blue links with visible
  keyboard focus; responsive sidebar; no analytics, emojis or external font calls.
- STIX Two Text is distributed under the SIL Open Font License; see
  `assets/fonts/STIX-OFL.txt`. The included Academicons and Font Awesome fonts
  come from the Academic Pages template.
- The verified publication and abstract come from
  https://arxiv.org/abs/2512.16021 and https://doi.org/10.1103/b8vm-fz49.
  Journal metadata was cross-checked against Crossref.
- The two thesis titles, years and institution match the supplied Google Scholar
  screenshot. Marek supplied both original abstracts and direct PDF links.
  The abstracts are reproduced as supplied, with the spelling correction
  “timedependent” → “time-dependent” in the bachelor's abstract.
  The bachelor's university record is
  https://dspace.cuni.cz/handle/20.500.11956/182563.
  Scholar's live profile rejected this browser's automated requests, so the
  screenshot is the source for checking the three-item list.
- Theme internals in `_sass/`, `_includes/`, `_layouts/` and the original npm
  scripts are retained for compatibility. The personal layout loads only
  `assets/css/profile.css`; the old example pages and publications were removed.

## Preview and verification

[Desktop preview](docs/preview-desktop.jpg) · [Verification notes](docs/verification.md)
