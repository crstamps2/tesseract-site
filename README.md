# tesseract.codystamps.dev

Marketing site + privacy policy for the **Tesseract Launcher** Android app.

Plain static HTML/CSS — no build step, no frameworks, and no third-party
requests (no external fonts, analytics, or CDNs).

```
index.html          landing page
privacy/index.html  privacy policy  ->  https://tesseract.codystamps.dev/privacy/
styles.css          shared styles
assets/             screenshots (replace the placeholders with polished shots)
CNAME               custom domain for GitHub Pages
```

## Deploy (GitHub Pages)

1. Create a repo (e.g. `tesseract-site`) and push this folder to `main`.
2. Repo **Settings → Pages**: set *Source* = "Deploy from a branch", branch
   `main`, folder `/ (root)`.
3. **Settings → Pages → Custom domain**: enter `tesseract.codystamps.dev`
   (the `CNAME` file already pins this), then tick **Enforce HTTPS** once the
   certificate provisions.
4. At your DNS provider for `codystamps.dev`, add:

   ```
   CNAME   tesseract   crstamps2.github.io.
   ```

   (Use your GitHub username’s `*.github.io` host.) Allow a few minutes for DNS +
   the Let’s Encrypt certificate. `.dev` is HSTS-preloaded, so the site must be
   HTTPS — GitHub Pages handles that automatically.

## After it’s live

Put the privacy URL into the Play Console listing:

```
https://tesseract.codystamps.dev/privacy/
```

## To update

Edit the HTML and push — GitHub Pages redeploys on every push to `main`.
Replace `assets/screenshot-*.png` with final marketing screenshots when ready.
