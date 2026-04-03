# Bertille Daran Website Editing Guide

This website is built with Hugo and the PaperMod theme.

## 1. Important files

- `config.yml`: homepage text, menu, social links, site-wide settings
- `static/profile.jpg`: profile photo shown on the homepage
- `static/cv.pdf`: PDF used by the CV page
- `static/jmp.pdf`: job market paper PDF
- `content/research/`: research pages
- `content/teaching/`: teaching pages
- `content/talks/`: talks and conference pages
- `content/location.md`: office and map page
- `content/cv.md`: CV page with embedded PDF

## 2. How to change the homepage text

Edit `config.yml`.

The main text on the homepage is in:

- `params.profileMode.title`
- `params.profileMode.subtitle`
- `params.profileMode.buttons`
- `params.socialIcons`

Examples:

- change your displayed name: edit `params.profileMode.title`
- change your bio: edit `params.profileMode.subtitle`
- change the button labels or destinations: edit `params.profileMode.buttons`
- change email, GitHub, LinkedIn, Scholar, or location links: edit `params.socialIcons`

## 3. How to change the profile picture

Replace `static/profile.jpg` with a new image using the same filename.

If you want a different filename, also update this line in `config.yml`:

`params.profileMode.imageUrl`

Recommended format:

- JPG or PNG
- square or close to square
- around 600 x 600 px or larger

## 4. How to change the menu

Edit the `menu.main` section in `config.yml`.

Current items are:

- Research
- Teaching
- Talks
- CV

Each item has:

- `name`: displayed label
- `url`: destination
- `weight`: order in the menu

## 5. How to edit research content

All research pages are in `content/research/`.

Each subfolder is one page bundle and must contain an `index.md`.

Current examples:

- `content/research/from-farm-to-cop/index.md`
- `content/research/obesity-reviews-2023/index.md`
- `content/research/world-development-perspectives-2022/index.md`

To edit text:

1. Open the page's `index.md`.
2. Update the front matter at the top.
3. Update the body text below the second `---`.

Useful front matter fields:

- `title`
- `date`
- `summary`
- `description`
- `tags`
- `author`

To add a new research page:

1. Create a new folder inside `content/research/`.
2. Add an `index.md` file.
3. Copy an existing research page and modify it.

## 6. How to edit teaching content

Teaching pages are in `content/teaching/`.

Current examples:

- `content/teaching/microeconomics-1/index.md`
- `content/teaching/microeconomics-2/index.md`

Use the same workflow as for research pages.

## 7. How to edit talks and conference content

Talk pages are in `content/talks/`.

Current examples:

- `content/talks/year-2026/index.md`
- `content/talks/year-2025/index.md`
- `content/talks/year-2024/index.md`
- `content/talks/year-2023/index.md`

You can either:

- keep one page per year
- create one page per event

## 8. How to change links to PDFs

Static PDFs live in `static/`.

Examples:

- `static/cv.pdf`
- `static/jmp.pdf`

Links to those files can be written directly as:

- `/cv.pdf`
- `/jmp.pdf`

If you replace the PDF with a different filename, update the links everywhere the old filename appears.

## 9. How to edit the location page

Edit `content/location.md`.

That page already contains:

- office addresses
- embedded Google Maps iframes

You can change:

- office name
- room number
- postal address
- iframe embed URL

## 10. How to preview locally

Make sure Hugo Extended is installed and available on your PATH.

Useful commands:

```powershell
hugo server -D
```

This starts a local preview server, usually at `http://localhost:1313/`.

For a production build:

```powershell
hugo --gc --minify
```

Generated files will appear in `public/`.

## 11. How deployment works

Deployment is handled by GitHub Actions with:

- `.github/workflows/hugo.yml`

The workflow builds the site from the `main` branch and deploys it to GitHub Pages.

Required GitHub setting:

- in the repository's Pages settings, the source should be `GitHub Actions`

## 12. Common update recipes

### Change your bio text

Edit `config.yml`, then change `params.profileMode.subtitle`.

### Change your email

Edit the `Email` item in `params.socialIcons` inside `config.yml`.

### Add a new paper

1. Create `content/research/new-paper-slug/`
2. Add `index.md`
3. Copy front matter from an existing research page
4. Add text and links

### Replace the CV

1. Replace `static/cv.pdf`
2. Keep the same filename if possible
3. Check `content/cv.md`

### Replace the profile photo

1. Replace `static/profile.jpg`
2. Keep the same filename if possible
3. Check `config.yml`

## 13. Notes on old demo content

The original demo sections from the template were kept in the repo but marked as drafts so they do not surface on the rebuilt site:

- `content/books/`
- `content/courses/`
- `content/data/`
- `content/papers/`

They can be deleted later if you no longer need them.
