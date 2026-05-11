# crimux

**The Criminologist's Guide to User Research of Apps and Tech** — an open-access handbook by Tara Abrahams (first author) and Scott Jacques (second author), hosted at [crimux.com](https://crimux.com).

## What this is

A ~6,000-word, four-part handbook that translates user research (UXR) for criminologists and makes criminology legible to UXR teams working on justice-tech. It ships with:

- Four short, skimmable parts (~1,500 words each).
- A curated ~75-entry annotated bibliography of justice-tech UX studies.
- Two interactive modules: a UXR-fit quiz and a Skills Translator.
- A "Cite this" page with DOI, BibTeX, APA, and Chicago entries.

## Who it's for

- Criminology PhDs and faculty curious about pivoting toward (or partnering with) UXR.
- UXR teams at justice-tech, civic-tech, and adjacent companies who want a citation-rich starting point.
- Funders, conference organizers, and journal editors who want a single open-access reference.

## Tech

- **Stack:** [Astro 4](https://astro.build) (static-site generator) with [`@astrojs/sitemap`].
- **Hosting:** Cloudflare Pages, deployed from `main` of [github.com/crimux/handbook](https://github.com/crimux/handbook).
- **Domain:** [crimux.com](https://crimux.com) — see `DEPLOY.md` for the click-path.
- **Fonts:** Inter + Fraunces, self-hosted via `@fontsource/*`. No external font CDN.
- **Analytics:** Cloudflare Web Analytics only (placeholder in `src/layouts/Base.astro`).
- **Accessibility target:** WCAG 2.2 AA.
- **Performance target:** Lighthouse ≥ 95 across the board.

## Run locally

```bash
nvm use            # uses .nvmrc (Node 20)
npm install
npm run dev        # http://localhost:4321
npm run build      # outputs to ./dist
npm run preview
```

## Project layout

```
src/
  components/   reusable Astro components
  data/         site config + JSON content (bibliography, quiz, translator)
  layouts/      Base.astro (head, header, footer, OG/Twitter metadata)
  pages/        index, parts/, bibliography, quiz, translator, cite, about, 404
  styles/       tokens.css (design tokens) + global.css
public/         static assets (favicon, OG images, robots, redirects)
```

## Editing content

See `CONTENT.md` for where to edit each part of the handbook, how to add a bibliography entry, and how to publish a new version with a Zenodo DOI.

## License

- **Content** (prose, bibliography annotations, quiz copy): [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
- **Code** (Astro components, configs, scripts): MIT — see `LICENSE`.

## Citation

See [`/cite`](https://crimux.com/cite) on the live site or the `CITATION.cff` in this repo.

> Abrahams, T., & Jacques, S. (2026). *The Criminologist's Guide to User Research of Apps and Tech* (v0.1.0) [Open-access handbook]. crimux.com. https://doi.org/10.5281/zenodo.PENDING
