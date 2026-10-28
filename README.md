# Apostolos Modas — Minimal Academic Website

A single-page static site that works on GitHub Pages, with no build step, package manager, or framework.

## Local preview

1. Extract the ZIP.
2. Open `index.html` in Chrome, Edge, or Firefox. Or open this folder in VS Code.
3. Edit text in `index.html`, save, and refresh the browser.
4. Edit visual styles in `styles.css`.

## Files

- `index.html` — all biography, work, publications, and links
- `styles.css` — typography, colors, spacing, responsive layout
- `assets/Apostolos_Modas_CV.pdf` — copy of the uploaded CV; replace when updating
- `assets/favicon.svg` — tiny browser icon
- `.nojekyll` — keeps GitHub Pages static hosting simple

### Optional portrait

Add a photo as `assets/portrait.jpg`. In `index.html`, find the `portrait-placeholder` element and replace it with:

```html
<img class="portrait-photo" src="assets/portrait.jpg" alt="Portrait of Apostolos Modas">
```

Add to `styles.css`:

```css
.portrait-photo {display:block;width:206px;height:222px;object-fit:cover;border-radius:7px}
```

The placeholder is deliberately an initials monogram until you provide a photo.

## Publish on GitHub Pages

1. Sign in to GitHub as `amodas`.
2. Create a **public** repository called `amodas.github.io` (unless you already have that user site).
3. Upload the **contents** of this folder into the repository root, so `index.html` is at the root, not inside another folder.
4. In Settings → Pages, select Deploy from a branch, `main`, `/(root)`.
5. Your expected URL will be https://amodas.github.io/ after Pages publishes.
6. Commit edits to update it later.

## Analytics: Cloudflare Web Analytics

1. Publish the site first.
2. In Cloudflare, visit Web Analytics and add `amodas.github.io`.
3. Choose the manual JavaScript installation method (Cloudflare doesn't automatically inject analytics into GitHub Pages).
4. Copy your site's unique beacon snippet and paste it in `index.html` where the `CLOUDFLARE ANALYTICS` comment appears, inside `<head>`.
5. Publish the commit and use the Cloudflare dashboard for page views, approximate unique visitors, and traffic sources.

Tracking is **not enabled by default**. Cloudflare's unique-visitor counts are estimates, not reliable person-level identities, and ad/tracker blockers may affect coverage.

## Before publishing

- Review public disclosure of your ongoing or under-review research.
- Check publication wording and all links.
- Check that your CV PDF is the one you want publicly accessible.
- Consider replacing the initials block with your portrait.

## Accessibility

Semantic HTML, keyboard-visible link focus, mobile-friendly layout, skip link, and reduced-motion support are included.

## Version 3 changes
- The previous Background section has been integrated into the introduction (About).
- Four lightweight SVG illustration thumbnails have been added to **Selected work**. They are conceptual illustrations, not original publication figures. Edit or replace `assets/*.svg` with your own paper figures/screenshots later.
- No publication filters, JavaScript frameworks, or tracking by default.

## Profile sidebar
The title, Sony AI affiliation, and five clickable icons are in the `portrait-wrap` block of `index.html`. Links are labeled for screen readers and show tooltips on hover. To add your photo, replace the `portrait-placeholder` element with the `portrait-image` example in the adjacent HTML comment, and put your `portrait.jpg` under `assets/`. The sidebar also appears on mobile.

## Version 5: Contact section and publication thumbnails

- The **Contact** button in the top navigation scrolls to `#contact`, where the email is displayed as `apostolos.modas[at]gmail.com`. The existing envelope icon below the portrait still opens an email client.
- Every publication now has a thumbnail **on its left**, between the year and paper title. The initial six SVGs in `assets/publications/` are intentionally generic placeholders, **not figures from the papers**.
- To use real paper images: place a `.png`, `.jpg`, `.webp` or `.svg` in `assets/publications/`, then modify the corresponding `<img src="assets/publications/...">` in `index.html`. For example, change `assets/publications/prime.svg` to `assets/publications/prime-figure.png`.
- Thumbnail sizing and responsiveness are controlled by `.pub-thumbnail` in `styles.css`; images are cropped to fit using `object-fit: cover`. For important scientific figures that should not be cropped, change it to `object-fit: contain` (and consider a light background).
- Before publishing actual paper figures, confirm that you have rights to reuse them on a personal website.


## v6: Circular profile photo and navigation

The top navigation is **About · Work · Publications · Contact · CV**.

To replace the round `am.` placeholder with your photo:

1. Put your photo at `assets/portrait.jpg` (a square crop with space around the face works best).
2. In `index.html`, find the `<div class="portrait-placeholder" ...>` and replace that entire element with:

   ```html
   <img class="portrait-image" src="assets/portrait.jpg" alt="Portrait of Apostolos Modas">
   ```

3. Save and refresh your browser. The CSS automatically crops a rectangular source photograph into a **circle**. Adjust `object-position: center 30%` in `styles.css` if needed.

Your social links, publication thumbnails, Contact section, CV, and optional analytics remain unchanged.
