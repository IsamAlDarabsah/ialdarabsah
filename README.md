# ialdarabsah.github.io

Personal academic website. Plain HTML and CSS — no build step, no Jekyll, no
dependencies. Every file can be edited directly in the GitHub web editor.

## Files

| File | What it is |
|---|---|
| `index.html` | Homepage: bio, background, recent work, contact |
| `research.html` | Research themes |
| `publications.html` | Publication list by year |
| `teaching.html` | Courses and supervision |
| `404.html` | Shown when a link is broken |
| `style.css` | All styling; colours and fonts are at the top |
| `.nojekyll` | Tells GitHub to serve the files as-is |

Delete `_config.yml` from the repo — it is Jekyll configuration and this site
does not use Jekyll. The page title and description now live in the `<title>`
and `<meta name="description">` tags of each HTML file.

## Still to fill in

1. **Email.** Replace `CHANGE-ME@just.edu.jo` (appears in `index.html` twice
   and `404.html` once).
2. **Google Scholar.** Replace `scholar.google.com/citations?user=XXXX` in
   `index.html` with your profile URL, or delete that link.
3. **Office.** `index.html`, contact list — "Building, Room".
4. **Publications.** `publications.html` has your two 2025 papers with DOIs.
   The rational-links paper needs its volume and year checked, and there is one
   empty template entry to copy for everything else.
5. **Teaching.** The "Previously" block on `teaching.html` is a template.
6. **CV.** Upload `cv.pdf` to the repo root; the nav link already points at it.

Press `.` while viewing the repo on GitHub to open the browser editor, where
search-and-replace works across all files at once.

## Adding a publication

Copy an `<article class="pub">` block and edit it. The year label comes from
the `<div class="margin">` of the surrounding section, so put the entry under
the right year or add a new section.

## Adding a photo

Upload `photo.jpg`, then add this in `index.html` just before the `<h1>`:

```html
<img src="photo.jpg" alt="" width="120" height="120"
     style="border-radius:50%;margin-bottom:1.5rem;object-fit:cover;">
```

## Mathematics

MathJax is loaded on every page, so `$\mathcal{R}_0$` and `$\dot{N} = rN(1-N(t-\tau))$`
render as mathematics anywhere in the text.

## Colours

All from the variables at the top of `style.css`:

```css
--paper:    #F6F7F5;   /* page background */
--ink:      #16221E;   /* text            */
--viridian: #2E6A57;   /* links, curves   */
--amber:    #97662F;   /* data labels     */
```

## The curves on the homepage

Numerically integrated solutions of the delayed logistic equation
$\dot{N} = rN(1 - N(t-\tau))$ at four delays, showing the transition from
monotone approach through damped oscillation to a sustained oscillation past
the Hopf point at $r\tau = \pi/2$. To remove them, delete the whole
`<section class="curveband">` block in `index.html`.

## Custom domain

Settings → Pages → Custom domain, then add a CNAME DNS record pointing at
`ialdarabsah.github.io` and tick *Enforce HTTPS*.
