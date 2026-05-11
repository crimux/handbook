# CONTENT.md — editing the handbook

## Where to edit each part

| Part | File |
| ---- | ---- |
| Home page | `src/pages/index.astro` |
| Part 1 — What is UXR, actually? | `src/pages/parts/1-what-is-uxr.astro` |
| Part 2 — What criminology already knows | `src/pages/parts/2-what-criminology-knows.astro` |
| Part 3 — Open problems | `src/pages/parts/3-open-problems.astro` |
| Part 4 — UXR as a career | `src/pages/parts/4-careers.astro` |
| About / authors | `src/pages/about.astro` |
| Cite this | `src/pages/cite.astro` |

Headings, callouts, pull-quotes, and the "Sources & Further Reading" box are all components — see `src/components/`.

### Conventions

- **Voice:** practitioner, plain-language, co-authorship-neutral. Use "we" only where it reads naturally. No first-person anecdotes that imply one author.
- **Citations:** end-of-section `<SourcesBox>` boxes with 3–6 items each. Hover-tooltips sparingly. Fewer than 15 true footnotes across the whole document, reserved for genuine asides.
- **Word counts:** ~1,500 words per part, ~6,000 total.

## Adding a bibliography entry

The bibliography is JSON-driven. Edit `src/data/bibliography.json` and append an object:

```json
{
  "id": "lastname2024short",
  "citation": "Lastname, F. M. (2024). Title. Journal, 12(3), 100–120.",
  "doi": "10.1234/abcd.5678",
  "oa_url": "https://example.org/pdf",
  "annotation": "80 words. What the study does, its method, its punchline. Skip the preamble.",
  "why_uxr": "Why a UXR practitioner would cite this in a research plan or readout.",
  "method": "interviews",
  "user_type": "incarcerated",
  "difficulty": "foundational",
  "year": 2024
}
```

### Tag vocabularies

- **method:** `interviews`, `observation`, `survey`, `usability`, `log-analysis`, `mixed-methods`, `desk-research`, `experiment`.
- **user_type:** `incarcerated`, `supervised`, `officers`, `court-staff`, `victims`, `attorneys`, `analysts`, `general-public`.
- **difficulty:** `foundational`, `advanced`, `niche`.

The bibliography page renders filter dropdowns from the data itself, so new tag values are picked up automatically.

## Inclusion bar (strict)

If an entry can't earn a non-obvious 80-word annotation that a UXR practitioner would care about, cut it. The whole point is signal density.

## Editing the quiz

`src/data/quiz.json`. The schema is documented inline:

- `dimensions` — the five sub-dimensions; an `id` and `label`.
- `questions` — each item references one `dim`. Phrase as a statement; the UI uses a 1–5 agree/disagree scale.
- `bands` — the four score bands (Not yet / Curious / Strong fit / Ready to apply) and their blurbs.

Scoring logic is in the inline `<script>` in `src/pages/quiz.astro`. Each item is rescaled from 1–5 to 0–100 per sub-dimension; the composite is the mean of the five.

## Editing the Skills Translator

`src/data/translator.json`. Each mapping has:

- `match` — array of substrings (lowercased) that trigger this rule.
- `uxr` — the UXR-equivalent label.
- `frame` — a 1–2 sentence resume/cover-letter frame.

A fallback mapping at the bottom handles unmatched inputs. The matcher is greedy on first match in order, so put the more-specific rules first.

## Publishing a new version

1. Bump the version in:
   - `src/data/site.ts` → `version`, `lastUpdated`.
   - `CITATION.cff` → `version`, `date-released`.
   - `package.json` → `version`.
2. Update `src/data/site.ts` → `doi` to `10.5281/zenodo.PENDING` until you mint a new Zenodo DOI for this version.
3. Commit. Tag the release:
   ```bash
   git tag -a v0.2.0 -m "v0.2.0 — short summary"
   git push origin v0.2.0
   ```
4. **Zenodo deposit:**
   - Make sure the GitHub repo is connected to Zenodo (toggle on at https://zenodo.org/account/settings/github/). The first release after the toggle is the one Zenodo will start archiving.
   - Create a GitHub Release from the tag. Zenodo auto-archives the source code and mints a DOI.
   - Copy the new DOI back into `src/data/site.ts` and `CITATION.cff` and push a small commit.
5. Cloudflare Pages auto-deploys on push to `main`.

## Adding a new top-level page

1. Add `src/pages/your-page.astro`, using `<Base title="…" description="…">`.
2. Add an entry to `nav` in `src/data/site.ts` if it belongs in the header.
3. The sitemap regenerates automatically on build.

## Images and OG cards

- Put OG images (1200×630 PNG) in `public/og/`. Pass `ogImage="/og/your-image.png"` to `<Base>`.
- The default OG image is `public/og/default.png` (placeholder shipped with the repo; regenerate before launch).
