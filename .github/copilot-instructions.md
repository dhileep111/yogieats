Guidance for AI coding agents working on this repository

Summary
- Small static marketing site with vanilla HTML/CSS/JS and an optional PHP contact endpoint.
- Primary entry: `index.html`. Repeated page templates live at the repo root (e.g. `about.html`, `services.html`, `team.html`, `one-column.html`, etc.).

Big picture / architecture
- No front-end framework or build system: pages are plain HTML that reference assets under `assets/`.
- Assets layout:
  - CSS: `assets/css/` (`style.css`, `custom-style.css`, `mediaqueries.css`, `special-classes.css`).
  - Bootstrap: `assets/bootstrap/bootstrap.min.css` and a local JS `assets/js/bootstrap.min.js` (note: some HTML files incorrectly use the JS file as a stylesheet; confirm before changing).
  - JS: `assets/js/` (jQuery, `animation.js`, `type.js`, `video-popup.js`, `video-section.js`, plus `bootstrap.min.js`).
  - Images and favicons: `assets/images/` and `assets/images/favicon/` (manifest.json present).
- Third-party libraries used via CDN: Font Awesome, AOS, Magnific Popup, Swiper. Also local copies of Bootstrap and jQuery.

Critical integration points
- Contact form: `contact-form.php` accepts POST and sends email via PHP `mail()`; it returns JSON. To test the form you must run a PHP-enabled server (see workflows).
- Google/analytics & verification: `google55551cdaff15094a.html` and inline gtag script in `index.html`.

Developer workflows (what actually works here)
- Local static preview: open `index.html` in a browser for most visual changes.
- PHP endpoint testing: run a local PHP server from the project root:

```bash
php -S localhost:8000
# then visit http://localhost:8000/index.html
```

- There is no `npm`, `yarn`, or other build step. Do not assume Sass/TypeScript or bundlers unless the repo is extended.

Project-specific conventions & patterns
- Page templates are duplicated HTML files (no templating engine). To edit a shared header/footer, update each HTML file that contains it.
- Naming: page variations indicate layout choices (e.g. `one-column.html`, `two-column.html`, `three-column.html`, `three-colum-sidbar.html`, `four-column.html`, `six-column.html`). Use these filenames when searching for layout-specific markup.
- CSS layering: keep global rules in `style.css`, responsive rules in `mediaqueries.css`, and per-component overrides in `custom-style.css` and `special-classes.css`.
- JS interactions: look into `assets/js/type.js` for typed text on the hero, `animation.js` and AOS for scroll reveals, and Swiper for testimonial sliders.

Patterns to follow in PRs/edits (concrete examples)
- Changing site copy or meta tags: update `index.html` and other root HTML files — there is no single source-of-truth file.
- Updating the navbar: edit `index.html` and every page that contains the duplicated navbar markup. Example: the nav appears in the top of `index.html` and `about.html`.
- Fixing the contact form: `contact-form.php` posts back JSON. If you change response shape, update any client-side JS expecting `{status,msg}`.
- When adding dependencies, prefer CDN links for lightweight additions (consistent with existing code) unless the user asks to commit vendor code.

Gotchas and discovered issues
- HTML bug: `index.html` contains `<link rel="stylesheet" href="./assets/js/bootstrap.min.js">` — this is a JS file linked as CSS. Verify and correct to a `<script>` tag when fixing assets.
- The PHP mail function is used without additional sanitization or SMTP configuration — modifying server-side email behavior requires validating the environment and credentials.

Suggested prompt templates for agent tasks
- "Update the site title and meta description in all root HTML files to: <new text>. List modified files." (agent should grep for `<title>` and `<meta name="description">` and edit each HTML file.)
- "Make the 'Home' nav item active across pages: set `.nav-item.active` only on `index.html` and remove `active` from others." (agent should edit all HTML files containing the nav.)
- "Fix the bootstrap include issue in `index.html` by replacing the incorrect CSS link to `assets/js/bootstrap.min.js` with a proper `<script>` tag at the end of the body." (provide patch and test instructions.)

If you need clarification
- Ask which files should be used as the canonical header/footer (there is currently no template file).
- Request permission before changing `contact-form.php` or email behavior — server-side changes require environment access.

After making edits, test steps
- For pure HTML/CSS/JS changes: open `index.html` and several other pages in a browser to verify layout and assets.
- For contact form changes: run `php -S localhost:8000` and submit the contact form; inspect network response JSON.

If this file is incomplete or you want a different focus, tell me which areas to expand (testing, CI, templating migration, or security hardening).
