Guidance for AI coding agents working on this repository

Summary
- Small, static marketing site built with plain HTML/CSS/JS and an optional PHP contact endpoint.
- Primary entry: index.html. Page variants (about, services, team, pricing, column layouts) live at the repository root.

Big picture — architecture at a glance
- No bundler or framework: pages are static HTML referencing files under ssets/.
- Assets layout (use these paths when editing):
  - CSS: ssets/css/ (style.css, custom-style.css, mediaqueries.css, special-classes.css).
  - Bootstrap (CSS): ssets/bootstrap/bootstrap.min.css.
  - JS: ssets/js/ (local jquery-3.6.0.min.js, nimation.js, 	ype.js, ideo-popup.js, ideo-section.js, ootstrap.min.js).
  - Images/favicons: ssets/images/ and ssets/images/favicon/.
- Third-party libs often used via CDN (Font Awesome, AOS, Magnific Popup, Swiper). Prefer CDN unless instructed otherwise.

Critical integration points
- Contact form: contact-form.php accepts POST and returns JSON; it uses PHP mail(). To test, run a PHP-enabled server (see workflows).
- Google verification & analytics: google55551cdaff15094a.html plus an inline gtag snippet in index.html.

Developer workflows (what actually works)
- Quick preview: open index.html (or any root HTML) in a browser for visual checks.
- Contact endpoint testing: from project root run:

`ash
php -S localhost:8000
# then visit http://localhost:8000/index.html
`

- There is no 
pm/yarn or build step. Do not assume Sass/TS or bundlers.

Project conventions and patterns (important)
- Header/footer and navbar are duplicated across root HTML files — there is no templating engine. Edit each HTML file when changing shared chrome.
- File naming reflects layout variants (e.g., one-column.html, 	hree-column.html, 	hree-colum-sidbar.html). Use these names when searching for layout-specific markup.
- CSS layering: global rules in style.css, responsive rules in mediaqueries.css, per-component overrides in custom-style.css and special-classes.css.
- JS behaviors: typed hero text in ssets/js/type.js, scroll reveals in nimation.js (AOS), and sliders via Swiper — inspect those files when modifying interactions.

Repair patterns and common PR tasks
- Change site copy/meta: update index.html and any other root HTML files directly; grep for <title> and <meta name= description>.
- Make nav active: set .nav-item.active only in index.html and remove ctive from other pages.
- Contact form changes: contact-form.php returns {status,msg}; if you change the shape, update any client JS that reads the response.
- Add dependencies: Prefer CDN links (consistent with repo style). If adding local vendor files, place them under ssets/ and update affected HTML pages.

Known gotchas (do not overlook)
- Incorrect asset include: index.html currently contains <link rel=stylesheet href=./assets/js/bootstrap.min.js> — this links a JS file as CSS. Replace with a <script src=assets/js/bootstrap.min.js></script> placed before </body> when fixing.
- contact-form.php uses PHP mail() without SMTP configuration — changing server-side email behavior requires environment access and credential configuration.

Files to check first when editing
- Primary pages: index.html, bout.html, services.html, 	eam.html, contact.html.
- Contact: contact-form.php.
- Assets: ssets/css/, ssets/js/, ssets/bootstrap/bootstrap.min.css, ssets/js/bootstrap.min.js.

Small examples you can use as prompts
- Replace the incorrect bootstrap CSS link in index.html with a <script> tag and place it before </body>. Provide a patch and test steps.
- Update meta description across all root HTML files to: [new text]. List modified files.

Testing & validation
- Static changes: open affected HTML files in a browser to visually validate.
- Contact form: run the PHP server above and submit the form; inspect network response JSON and server logs.

If something's missing
- Ask which root HTML files should become canonical for shared chrome (header/footer). I can refactor and apply consistent changes once you confirm.

-- End of guidance
