# Round 2 Research Briefing — crimux.com bibliography

We have 23 entries in `src/data/bibliography.json` and need to add ~50 more to reach ~75 total. The bar is strict: every entry must earn a non-obvious eighty-word annotation that tells a UX researcher something they could not learn from the title or one-sentence abstract.

## Subject areas + current counts + targets

| subject_area | current | target | gap |
|---|---|---|---|
| inmate-tablets | 2 | 8 | +6 |
| parole-apps | 3 | 8 | +5 |
| bwc | 3 | 9 | +6 |
| predictive-policing | 3 | 9 | +6 |
| e-filing | 3 | 8 | +5 |
| victim-notification | 2 | 7 | +5 |
| tip-lines | 3 | 7 | +4 |
| digital-evidence | 2 | 7 | +5 |
| jail-visitation | 2 | 6 | +4 |
| **TOTAL** | **23** | **69** | **+46** |

(BWC and predictive policing have the richest literatures — push to 9 each. Jail visitation will likely top out around 6 given the thin literature; do not pad.)

## Existing IDs — DO NOT duplicate

```
opencampus2023tablets, wagnerwagner2017wireless, owens2022emapps,
cjtec2023supervisionapps, grommon2023gps, lum2019bwc, gaub2016bwcperceptions,
lum2020campbellbwc, stevenson2018kentucky, myhillhohl2023officer,
topper2024shotspotter, 18f2021cmecf, ncsc2023efiling, hagan2016legalux,
zweig2013savins, cjtec2024avn, hsieh2022saysomething, espelage2021tiplines,
steinserous2023safevoice, miller2022prosecutors, daye2023nij,
rabuy2015screening, ppi2019videofailure
```

## Held candidates from Round 1 — please evaluate first

These 15 surfaced in Round 1 but were not picked for the first 25. Re-check each: if it earns a non-obvious 80-word annotation, include it.

- finkel2019tablets (PPI 2019 free-tablet contracts deeper analysis)
- pewtrusts2016em (Pew Charitable Trusts 2016 electronic monitoring use)
- uscourts2007gpsofficers (US Courts 2007 GPS for federal officers)
- geis2006challenges (Geis 2006 challenges to EM)
- jennings2014bwc (Jennings et al. 2014 Orlando BWC RCT)
- perf2014bwcguide (PERF 2014 implementing a BWC program)
- stevensonDoleac2018roadblock (Stevenson & Doleac 2018 algorithmic risk assessment paper)
- pacersurvey2021 (PACER 2021 user survey — federal court records)
- mentovichetal2023odr (Mentovich et al. 2023 online dispute resolution UX)
- ncsc2021odrtoolkit (NCSC 2021 ODR implementation toolkit)
- irazola2016icpsr (Irazola et al. 2016 victim notification ICPSR archive)
- espelage2016soars (Espelage 2016 SOARS school anonymous reporting)
- ojp2015digitalevidence (OJP 2015 digital evidence basics)
- vera2024videovisits (Vera Institute 2024 video visit impact)
- tandfonline2023videochildren (2023 children of incarcerated parents and video visits)

(Full Round 1 candidate table — 40 rows including 25 already used and these 15 held — is in `_research/bibliography_candidates.md`.)

## The bar (repeated for emphasis)

Every annotation must contain at least one of:
- a specific numeric finding (effect size, sample n, base rate, time cost)
- a documented user behavior or workaround
- a methodological choice that matters (sampling, instrument, comparator)
- a contradiction the literature has not resolved
- a design constraint that emerges from the study

Out:
- bias audits with no human-factors content
- op-eds, press releases, vendor whitepapers, generic "tech adoption" pieces
- studies whose annotation is just a paraphrase of the abstract
- entries whose "why a UXR would cite this" is generic ("provides background on X")

If you can't write an annotation that meets the bar, drop the candidate.

## Subject-area research prompts (use these to seed searches)

### inmate-tablets (+6)
- Prison Policy Initiative briefings (Wanda Bertram, Peter Wagner) 2018–2025 beyond what we have
- Stickle & Schuster 2022 "carceral technology" qualitative work
- Wallace et al. on tablets in jails (re-entry preparation use)
- Davis et al. 2022 NIJ tablet research portfolio
- Vera Institute "Reimagining Prison" tablet pieces (post-2020)
- Inmate tablet content moderation / book censorship research
- The Marshall Project & Open Campus reporting that includes user interviews
- HSL / Aleph Lab Stanford work on digital incarceration
- USENIX / SOUPS papers on prison communication apps
- Krasnowski / Bedoya / Crockford "The Carceral Web" work

### parole-apps (+5)
- Henneberger et al. studies on probation tech
- Beyond Charles' research on EM
- Rachel Lovell or others on victim/offender app overlap
- Sentinel Offender Services / BI Inc / SCRAM research
- Reentry app evaluations (Jail Education Solutions, APDS, Edovo when paired with reentry)
- Studies of cognitive-behavioral apps in probation (e.g., Tyburski et al.)
- Risk-needs-responsivity tools as apps (LSI-R, ORAS digital deployments)
- Pretrial Justice Institute studies on pretrial supervision apps
- Defendant-facing court date reminder studies (Bornstein et al. 2013 — classic)

### bwc (+6)
- Ariel et al. 2015 Rialto and follow-up critiques
- White, M. D. monograph series on BWCs
- Headley et al. studies on BWC perceptions of community members
- DOJ BWC Toolkit citizen-experience research
- Newell on BWC privacy / officer-discretion design
- BWC video review for accountability (BJA studies)
- Activation compliance studies (Wexler, Lawrence)
- Maskaly, Donner, Jennings reviews

### predictive-policing (+6)
- Brantingham et al. 2018 PredPol LAPD RCT
- Ferguson "Big Data Policing" empirical pieces
- Lum & Isaac 2016 "To predict and serve?"
- Saunders et al. 2016 Chicago strategic subjects list evaluation
- Selbst on "disparate impact in big data policing"
- Mohler et al. PredPol evaluations
- Brayne 2017 "Big Data Surveillance" (Sociology paper, fieldwork at LAPD)
- Eubanks "Automating Inequality" Allegheny case
- Skeem & Lowenkamp risk-assessment validation work
- Albright 2019 NYC pretrial risk study

### e-filing (+5)
- ACUS (Administrative Conference) reports on PACER usability
- World Justice Project measurement of court tech
- Pew (Pew Charitable Trusts) work on civil legal access
- Frontiers / a2j research (Stanford Legal Design Lab beyond Hagan 2016)
- IAALS studies on family law e-filing
- Sandefur on legal needs
- Adam Beberg / Pro Bono Net studies on self-help portals

### victim-notification (+5)
- NCVC / OVC technical assistance reports beyond CJTEC 2024
- Goodman-Delahunty on victim communication preferences
- Long-term VINE evaluation (Office for Victims of Crime)
- McEwen 2002 (early SAVIN piece, classic)
- Garcia-Moreno on tech-mediated victim support (WHO)
- Brewer et al. 2018 on tech-facilitated abuse and survivor support apps
- Survivor-led app research (Project Callisto, etc.)
- Probation/parole VINE-Court integration studies

### tip-lines (+4)
- Crime Stoppers academic evaluations
- Texas iWatchTexas, Colorado Safe2Tell empirical studies
- Sandy Hook Promise Say Something curriculum studies
- Pollack et al. on threat assessment and reporting
- Anonymity-affordance research (HCI literature on anonymous reporting tools)

### digital-evidence (+5)
- DOJ FBI Cellebrite/Graykey procurement reports with workflow data
- Garfinkel 2010 "Digital forensics research: The next 10 years"
- Casey "Digital evidence and computer crime" excerpted research
- SWGDE (Scientific Working Group on Digital Evidence) practitioner studies
- Hargreaves & Patterson research on triage in digital forensics
- Quick & Choo digital forensic data reduction studies
- Sundaresan et al. 2021 on body-camera + digital-evidence integration
- IACP digital evidence reports

### jail-visitation (+4)
- Vera Institute reports on family contact post-2020
- Cochran & Mears family-contact reviews
- Skarupski / De Claire et al. on incarcerated parent contact effects
- Christian 2005 / Comfort 2008 on visitation experience (foundational, qualitative)
- Lindsey et al. 2017 video-visit acceptability
- Tasca et al. on visitation barriers (long line of empirical work)
- Rocque, Berg et al. on contact and recidivism

## Deliverable

Save a markdown file at `/home/user/workspace/crimux/_research/round2_candidates.md` with the same column structure as Round 1:

```
| id | citation (APA) | doi | oa_url | year | method | user_type | difficulty | subject_area | 80_word_annotation | why_a_uxr_would_cite_this |
```

Valid tag vocabularies:
- **method**: interviews, observation, survey, usability, log-analysis, mixed-methods, desk-research, experiment
- **user_type**: incarcerated, supervised, officers, court-staff, victims, attorneys, analysts, families, general-public
- **difficulty**: foundational, advanced, niche
- **subject_area**: inmate-tablets, parole-apps, bwc, predictive-policing, e-filing, victim-notification, tip-lines, digital-evidence, jail-visitation

Aim for ~65–70 candidates so I can curate 50 strong ones. Include 1–2 extra in jail-visitation if you find them, but do not pad. It is better to deliver 4 strong entries than 6 marginal ones in a thin area.

Use real DOIs and OA URLs. If a study is behind a paywall and has no OA copy, set `oa_url` to empty string. Verify each link actually resolves to the paper before listing it.

## Time budget

This is the largest single research pass for the project. Take the time to verify each citation. Spend extra effort on the 4 thin areas — that is where this round is judged.
