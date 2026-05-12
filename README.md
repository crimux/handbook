# crimux

**The Criminologist's Guide to User Experience: Making Criminal Justice Apps Work Better for the People Who Use Them** — an open-access handbook by Tara Abrahams (first author) and Scott Jacques (second author), published by the [CrimRxiv Consortium](https://www.crimrxiv.com/consortium) and hosted at [crimux.com](https://crimux.com).

## What this is

A ~6,000-word, four-part handbook that translates user experience (UX) research for criminologists and makes criminology legible to UX teams working on criminal justice technology. It ships with:

- Four short, skimmable parts (~1,500 words each).
- A curated ~75-entry annotated bibliography of user-experience studies in criminal justice technology.
- Two interactive modules: a UX-fit quiz and a Skills Translator.
- A "How to cite" section on the About page with DOI, BibTeX, APA, and Chicago entries.

It is a service of the [CrimRxiv Consortium](https://www.crimrxiv.com/consortium), part of our mission to make criminology useful. Free, open-access criminology research lives at [CrimRxiv](https://www.crimrxiv.com).

## Who it's for

- Criminology PhDs and faculty curious about pivoting toward (or partnering with) user-experience research.
- UX teams at criminal-justice-tech, civic-tech, and adjacent companies who want a citation-rich starting point.
- Funders, conference organizers, and journal editors who want a single open-access reference.

## Tech

- **Stack:** [Astro 4](https://astro.build) (static-site generator) with [`@astrojs/sitemap`].
- **Hosting:** Cloudflare Pages, deployed from `main` of [github.com/crimwork/handbook](https://github.com/crimwork/handbook).
- **Domain:** [crimux.com](https://crimux.com) — see `DEPLOY.md` for the click-path.
- **Fonts:** Source Serif 4 + Inter + JetBrains Mono, loaded from Google Fonts (matches the CrimRxiv Faculty Explorer aesthetic).
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

See `CONTENT.md` for where to edit each part of the handbook, how to add a bibliography entry, and how to publish a new version with a DOI.

## License

- **Content** (prose, bibliography annotations, quiz copy): [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
- **Code** (Astro components, configs, scripts): MIT — see `LICENSE`.

## Citation

See [`/about#cite`](https://crimux.com/about#cite) on the live site or the `CITATION.cff` in this repo.

> Abrahams, T., & Jacques, S. (2026). The Criminologist's Guide to User Experience: Making Criminal Justice Apps Work Better for the People Who Use Them (v0.2.0) [Open-access handbook]. CrimRxiv Consortium. https://doi.org/10.5281/zenodo.PENDING
