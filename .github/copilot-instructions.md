# Copilot / AI agent instructions for Marlyn-Akpofure-Portfolio-Website

Purpose: quickly orient an AI coding agent to what's safe and useful to change in this static portfolio template.

- Project type: static Bootstrap-based portfolio (SnapFolio template). No Node/npm build, no bundler. Main pages: `index.html`, `portfolio-details.html`, `service-details.html`, `starter-page.html`.
- Key folders: `assets/css/` (primary stylesheet: `main.css`), `assets/js/` (primary JS: `main.js`), `assets/img/` (profile, portfolio images), `assets/vendor/` (third-party libs), and `forms/` (server-side contact handler: `contact.php`).

Big picture & intent
- This is a mostly static site: HTML templates + vanilla JS that wires vendor libraries (AOS, GLightbox, Isotope, Swiper, Typed.js, PureCounter). Avoid introducing frameworks or build tools.
- Primary runtime is the browser; server-side surface is limited to `forms/contact.php` for form submission. Any backend work should respect that existing PHP handler.

Developer workflows
- No build step: open files in a browser or with a Live Server extension. Edits to `assets/css/main.css` and `assets/js/main.js` are served directly.
- If you change vendor code, prefer updating config or adding small wrappers in `assets/js/main.js` instead of modifying vendor files under `assets/vendor/`.

Project-specific conventions (examples)
- Typed hero text: edit the `data-typed-items` attribute on the `.typed` element in `index.html` to change rotating phrases. Example: <span class="typed" data-typed-items="Foreign Policy Professional, Research Specialist"></span>
- Image assets: portfolio/profile images are stored under `assets/img/profile/` and `assets/img/portfolio/` (names like `1.jfif`, `p1.jfif`). Keep naming consistent to avoid broken references in templates.
- Slider configs: Swiper JSON is embedded in DOM inside `.swiper-config` nodes; modify via `assets/js/main.js` init code if behavior changes are needed.
- Isotope layouts: markup uses `.isotope-layout` with data attributes (`data-layout`, `data-default-filter`, `data-sort`). Let `assets/js/main.js` handle initialization.

Integration points & external dependencies
- Vendor libs are located at `assets/vendor/` and are loaded directly from HTML. Examples: `assets/vendor/bootstrap/`, `assets/vendor/aos/`, `assets/vendor/glightbox/`, `assets/vendor/isotope-layout/`, `assets/vendor/swiper/`, `assets/vendor/typed.js/`.
- Contact form posts to `forms/contact.php`. Check that any form-field name changes are mirrored in that PHP file.

What to change vs what to avoid
- Change: content, CSS tweaks in `assets/css/main.css`, small behavior additions or bug fixes in `assets/js/main.js`, updating vendor versions carefully.
- Avoid: introducing a Node-based toolchain, converting the app into a SPA, or making sweeping rewrites that remove static HTML pages unless user explicitly requests.

Testing & validation
- Manual: open pages in a browser and verify interactive features (typed text, AOS animations, glightbox, isotope filters, swiper) and contact form submission.
- Linting/build: none provided. If you add tooling, include an explanatory note and backwards-compatible scripts.

Files to inspect for context
- Index and hero behavior: `index.html`
- Main site JS behaviors: `assets/js/main.js`
- Primary CSS: `assets/css/main.css`
- Contact integration: `forms/contact.php`

If something is unclear, show a short diff and ask before making structural changes.

---
Please review this file; tell me any gaps or additional examples you'd like included.
