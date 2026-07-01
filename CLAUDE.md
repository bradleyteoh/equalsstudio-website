# Equals Design Studio — marketing website

This is the public marketing site for **equalsstudio.com**. It is a **plain static HTML site** — no build step, no framework, no npm. Each page is a single `.html` file with its CSS inlined in a `<style>` block in the `<head>`.

You are most likely helping **a non-technical designer** edit content here (mainly adding portfolio work). Be concrete, make the change, preview it, and show the result. Don't assume they know HTML, git, or the terminal — do those parts for them.

## Guardrails — read first

- **Publishing = commit + push to `main`.** This repo is on Netlify, which **auto-deploys every push to `main`**. So pushing to `main` publishes to the live equalsstudio.com in ~1 minute. Treat it accordingly.
- **Always preview locally before committing** (see below). Never commit an unpreviewed change — a mistake on `main` goes live.
- **Do not run the Netlify CLI** (`netlify deploy` etc.) or touch `.netlify/`. Deployment happens automatically from the git push; the CLI is not needed.
- **Do not edit** `robots.txt`, `sitemap.xml`, the legal pages (`privacy.html`, `terms.html`, `refund.html`, `payment.html`), or `favicon.png` unless explicitly asked.
- **Keep the existing design.** Reuse the CSS variables and existing classes (below). Don't introduce new fonts, colors, or a CSS framework.

## Files

- `index.html` — the main one-page site: header/nav, hero, `#about`, `#services`, `#contact`, footer. **This is where the portfolio goes.**
- `privacy.html` / `terms.html` / `refund.html` / `payment.html` — legal pages (leave alone).
- `favicon.png`, `robots.txt`, `sitemap.xml`, `.netlify/` — infrastructure (leave alone).

## Design system (defined in `index.html` `:root`)

| Variable | Value | Use |
|---|---|---|
| `--black` | `#1A1A1A` | header/hero/footer background, body text |
| `--cream` | `#E8E0D3` | text on dark, services section background |
| `--light` | `#F5F2EE` | page background |
| `--mid`   | `#8C8278` | muted labels |
| `--font-sans` | Helvetica Neue stack | everything |

Section pattern: each section uses a small uppercase `.section-label`, an `<h2>`, then content. Cards use `.grid` + `.card`. Match this when adding anything.

## Adding a Portfolio section (the common task)

Portfolio lives as a new `<section id="portfolio">` in `index.html`, placed **after the Services block and before `#contact`**. Also add a `Portfolio` link to the header `<nav>` (`<a href="#portfolio">Portfolio</a>`).

Use the existing `.grid` / `.card` pattern so it matches the Services section. A project card should hold: a **photo**, the **project title**, and a **short description** (and optionally client/location/tags). Put project images in an `images/` folder at the repo root and reference them with a root-absolute path, e.g. `<img src="/images/project-name.jpg" alt="...">`. Add responsive `img` styling to the `.card` (full width, `border-radius`, `object-fit: cover`) if it's not there yet.

Keep alt text descriptive. Optimize large photos (they slow the site) — flag any image over ~500KB and offer to note it for Bradley.

## Preview locally

The site uses root-absolute paths (`/favicon.png`, `/privacy.html`), so **don't** open the HTML file directly — serve it:

```
python3 -m http.server 8000
```

from the repo root, then open **http://localhost:8000**. (If Python isn't available, `npx serve` works too.) When asked to "preview" or "show me the site," start this server and give them the link.

## Publishing a change

The site auto-deploys from `main`. When a change is done **and has been previewed and confirmed by the editor**:

1. Commit to `main` with a clear message (e.g. `Add Sunway office fit-out to portfolio`).
2. Push: `git push origin main`.
3. Tell the editor: "Pushed — the live site will update in about a minute at https://equalsstudio.com."

Only commit what the editor asked for and saw in the preview. If they're unsure, keep the work uncommitted (or on a branch) until they confirm — don't push a half-finished change to `main`, because it goes live.
