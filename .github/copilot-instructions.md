Project: redyi1116.github.io

Purpose
- Small personal static site made of plain HTML pages organized by date-like folders (e.g. `0930/`, `1007/`, `1014/`, `1021/`).

Big picture
- Pure static site (no build system). Each folder typically contains a standalone `index.html` and local assets (images like `p1.jpg`, `KKK.PNG`, `IMG_4882.PNG`).
- Pages use inline CSS or link to external CDN assets (e.g. `w3.css`, Google Fonts). No JS build or server-side code present.

What to change and what to avoid
- Safe edits: update or add HTML/CSS, optimize or replace images, fix broken relative paths, and add small JS for UX (vanilla only). Keep pages standalone.
- Avoid: adding heavy tooling, changing site structure without preserving existing relative paths, or assuming a backend.

Patterns & conventions (examples from repo)
- Relative asset paths: images referenced locally next to each `index.html` (e.g. `1014/KKK.PNG`, `1021/IMG_4882.PNG`). Preserve this layout when moving or renaming files.
- Inline styles: many pages include page-specific <style> blocks inside `index.html` (see root `index.html` and `1014/index.html`). Prefer editing inline styles or adding a small `assets/` CSS if you must reuse styles across pages.
- External CDNs: some pages link to CDNs (e.g. `https://www.w3schools.com/w3css/5/w3.css`, Google Fonts). Keep CDN links intact unless updating to newer versions.

Editing guidelines for AI agents
- When updating HTML, run a quick local smoke check by opening the edited file in a browser to verify relative image links and layout.
- If creating shared assets (CSS/JS), place them in a new top-level folder `assets/` and update pages with relative links (e.g. `<link rel="stylesheet" href="/assets/site.css">`). Note: use root-relative (`/assets/...`) only if you intend to host from the repo root.
- Preserve language attribute `lang="zh-Hant"` found in several pages.

Common fixes examples
- Broken image: check file name case and path (Windows is case-insensitive, hosting may be case-sensitive). Example: `1014/KKK.PNG` referenced by `1014/index.html`.
- Missing viewport/meta: add `<meta name="viewport" content="width=device-width, initial-scale=1.0">` to pages lacking it.

Integration & deployment notes
- This repo is a static GitHub Pages site (no build). Commits to `main` (or the default branch) can be served by GitHub Pages. Do not create build artifacts in the root.

Where to look
- Root `index.html` — main home page styles and layout examples.
- `1014/index.html`, `1021/index.html` — examples of page-local CSS and CDN usage.
- Each dated folder — canonical pattern for standalone pages and image placement.

If unclear
- Ask: should new shared assets be added or keep changes page-local? Confirm hosting branch if not `main`.

End of instructions.
