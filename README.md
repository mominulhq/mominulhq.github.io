# Your website — deployment guide

This is a complete static site: 5 pages, one stylesheet, no build step. Everything below is copy-paste.

## 1. Put it on GitHub Pages (free hosting under your GitHub account)

Since your GitHub username is `mominulhq`, the cleanest option is a **user site**, which gives you the URL
`https://mominulhq.github.io`.

1. On GitHub, create a new repository named **exactly** `mominulhq.github.io`.
2. Upload every file in this folder (`index.html`, `research.html`, `publications.html`, `cv.html`,
   `contact.html`, `README.md`, and the `assets/` folder) into the root of that repository — either by
   dragging them into the GitHub web UI ("Add file → Upload files"), or via git:
   ```
   git clone https://github.com/mominulhq/mominulhq.github.io.git
   cd mominulhq.github.io
   # copy all files from this folder in here
   git add .
   git commit -m "Launch site"
   git push
   ```
3. Go to the repo's **Settings → Pages**. Under "Build and deployment," source should already default to
   "Deploy from a branch," branch `main`, folder `/ (root)`. Save.
4. Within a minute or two, your site is live at `https://mominulhq.github.io`.

If you'd rather keep it as a project page instead (e.g. `mominulhq.github.io/academic-site`), name the repo
anything you like and enable Pages the same way — the URL will just include the repo name as a path.

## 2. One thing only you can add

- **Your CV PDF.** Export your CV to PDF, name it `cv.pdf`, and drop it in the same folder as `index.html`
  (repo root). The "Download CV" button on the CV page already points to `cv.pdf`.

Your headshot (`photo.jpg`) is already in place on the homepage — cropped square from the photo you sent. To
swap it for a different one later, just replace `photo.jpg` with a new image of the same name (square crop
works best), or point the `<img src="...">` line in `index.html`'s `.avatar` div at a new filename.

## 3. Filling in the four publications not yet listed

Your profile notes seven published papers; three have full citation details fetched from your Google Scholar
profile and are on the Publications page. I didn't fabricate the remaining four — send me the citations (or a
link to the specific Scholar entries) and I'll add them in the same format, or you can add them yourself by
copying an existing `<div class="pub">...</div>` block in `publications.html` and editing the text.

## 4. Editing anything else

Every page is plain HTML with inline-readable class names (`hero`, `card`, `pub`, `thread`, etc.) styled from
`assets/style.css`. To change wording, edit the text directly in the relevant `.html` file. To change colors
or fonts, edit the `:root { ... }` variables at the top of `assets/style.css` — every color and font in the
site is driven from those variables.
