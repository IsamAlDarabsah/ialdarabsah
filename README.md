# Academic personal website

A static site for an academic homepage. No build step, no Jekyll, no
dependencies to install — every file is plain HTML and CSS, so you can edit
all of it in the GitHub web editor.

## Files

| File | What it is |
|---|---|
| `index.html` | Homepage: name, short bio, selected work, news, contact |
| `research.html` | Research areas in more depth |
| `publications.html` | Full publication list, grouped by year |
| `teaching.html` | Courses and supervision |
| `404.html` | Shown when a link is broken |
| `style.css` | All styling. Colours and fonts are at the top |
| `.nojekyll` | Tells GitHub to serve the files as-is |

## Publishing it

1. Create a repository named `username.github.io` (your GitHub username,
   lowercase). Make it **Public**.
2. **Add file → Upload files**, drag in every file from this folder, commit.
3. **Settings → Pages → Build and deployment**. Set Source to
   *Deploy from a branch*, Branch to `main` / `/root`, save.
4. Wait a few minutes, then open `https://username.github.io`.

If `.nojekyll` does not appear after uploading, your browser hid it because
it starts with a dot. Use **Add file → Create new file**, type `.nojekyll` as
the name, leave it empty, and commit.

## What to change first

Search and replace across all five HTML files:

- `Firstname Lastname` → your name
- `you@just.edu.jo` → your email
- `Lastname, F.` → how your name appears in citations
- `USERNAME` → your GitHub username
- `scholar.google.com/citations?user=XXXX` → your Scholar profile
- `orcid.org/0000-0000-0000-0000` → your ORCID

Press `.` while viewing the repo on GitHub to open the browser editor, where
you can do this with one search-and-replace across the whole repo.

## Adding a publication

Copy one `<article class="pub">` block in `publications.html` and edit it. The
year comes from the `<div class="margin">` label on the section, so put the
entry under the right year block or add a new one.

## Adding your CV

Upload the PDF as `cv.pdf` in the repo root. The CV link in the navigation
already points at it.

## Adding a photo

Upload the image as `photo.jpg`, then add this inside the `<div class="wrap">`
of the hero section on `index.html`, just before the `<h1>`:

```html
<img src="photo.jpg" alt="" width="120" height="120"
     style="border-radius:50%;margin-bottom:1.5rem;object-fit:cover;">
```

## Mathematics

MathJax is loaded on every page, so `$\alpha$` and `$E_\alpha(-t^\alpha)$`
render as mathematics anywhere in the text.

## Changing the colours

Everything comes from the variables at the top of `style.css`:

```css
--paper:    #F6F7F5;   /* page background  */
--ink:      #16221E;   /* text             */
--viridian: #2E6A57;   /* links, curves    */
--amber:    #97662F;   /* data labels      */
```

## The curves on the homepage

The lines across the top of `index.html` are plotted from real values of the
Mittag-Leffler function $E_\alpha(-t^\alpha)$ for four fractional orders. If
you would rather not have them, delete the whole
`<section class="curveband">` block.

## Custom domain

Settings → Pages → Custom domain. Add a `CNAME` DNS record pointing at
`username.github.io`, then tick *Enforce HTTPS* once the certificate is issued.
