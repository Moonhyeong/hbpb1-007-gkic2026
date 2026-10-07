# HBPB1-007 · G-KIC-NST Partnering Day 2026 Landing Page

Partnering landing page for **HBPB1-007**, submitted to the **G-KIC-NST Partnering Day 2026** (Boston, MA) for pre-circulation to local VCs and industry experts.

**→ View landing page: https://moonhyeong.github.io/hbpb1-007-gkic2026/**

> ⚠️ **Do not rename this repository or change the published URL once the QR code has been distributed.**
> `qr/qr_hbpb1-007-gkic2026_navy.png` encodes this exact URL and is embedded in the submitted
> supporting material (`HBPB1-007_OnePager_GKIC2026.pdf`). Verified 2026-10-07 by rebuilding the QR
> matrix from the URL and matching all 2,401 modules against the saved PNG.
> The same constraint already applies to the sibling repository `hbpb1-007-biousa2026`, whose URL is
> printed in the 2026 BIO Europe booklet (p. 37).

---

## Relationship to the sibling page

| Repository | URL | Audience |
|---|---|---|
| `hbpb1-007-biousa2026` | `…/hbpb1-007-biousa2026/` | BIO-Europe 2026 (Köln) · BIO USA 2026 (San Diego). **URL fixed by printed booklet QR.** |
| `hbpb1-007-gkic2026` (this) | `…/hbpb1-007-gkic2026/` | G-KIC-NST Partnering Day 2026 (Boston) |

This page is a **copy of the verified sibling page with event branding changed only**. Scientific
content, figures, claims and layout are identical and were not re-edited — the sibling had already
been reviewed at 375 / 760 / 1280 px. If a scientific fact changes, update **both** pages.

**No BIO-Europe / BIO USA branding on this page.** Earlier drafts carried the past events as "Also at"
lines in the meta description, a hero badge, two *Featured At* rows and the footer; all were removed
on 2026-10-07 at the PI's instruction so the page reads as a G-KIC-only asset. The generator asserts
this — `build_landing.py` prints the count of surviving `BIO-Europe` / `BIO USA` / `San Diego` /
`Köln` strings and flags any as 🔴. Do not reintroduce them.

## Figure borders

The three data figures arrived with **three different borders baked into the PNGs** — `efficacy.png`
had a soft shadow plus an `#E9E9E9` line, `ocular-delivery.png` a 1 px `#A6A6A6` line, and
`iop-safety.png` none at all. Since `.data-figure` already supplies a uniform
`1px solid var(--border)` card, the baked borders are **stripped** instead of matched:
`../gkic-partnering-2026/figtrim.py` detects the border band on each side, removes the leftover
rounded-corner arcs, and crops to content. `build_landing.py` runs it over the copied images, and
`make_onepager.py` uses the same module for the PDF — so the web page and the one-pager agree.

Re-running `build_landing.py` re-copies the untrimmed originals from the sibling page and trims them
again, so the result is reproducible. **Do not hand-edit the PNGs in `images/`.**

## Event

- **Programme:** G-KIC-NST Partnering Day 2026 · KIST × NST Global Partnering
- **Venue:** Boston, MA
- **Dates:** November 2026 — `[확인 필요]` exact dates not yet published by 국제사업기획팀. Update the
  `DATES` constant in `../gkic-partnering-2026/build_landing.py` and re-run when confirmed.

## Audience

VC investors and industry experts reviewing KIST bio technologies for partnering and matching ahead
of the Partnering Day.

## Wording constraints (carried over — do not reintroduce)

- **No "MyD88-selective" framing.** SPR selectivity is ~2.1-fold and the vendor summary states
  *comparable affinity* to both adapters.
- **No NOAEL / LOAEL / MTD for the rabbit study.** It is a non-GLP preliminary study; use
  "no test-article-related findings at the highest dose tested".
- **"Candidate", not "therapy"** — the programme is preclinical.
- **Prevalence must separate scopes**: global AMD 196 M (2020) → 288 M (2040) (Wong et al.,
  *Lancet Glob Health* 2014) vs 7MM 93.3 M (2024) → 103.0 M (2034) (GlobalData). The 103 M figure is
  **not** a global number.

## Publication

Lim Y., Kang T.K., Kim M.I., Kim D., Kim J.Y., Jung S.H., Park K.\*, Lee W.-B.\*, Seo M.-H.\*
*Advanced Science* **2025**, 12(1), 2406018.
[doi.org/10.1002/advs.202406018](https://doi.org/10.1002/advs.202406018)

## Contact

- **Drug Discovery (Technology Transfer)** — Dr. Moon-Hyeong Seo, Principal Researcher, KIST · mhseo@kist.re.kr
- **Drug Development (BD)** — Huons BioPharma · Dr. Do Soo Jang, R&D Director · dosoo.jang@huonsbiopharma.com

## Deployment

```bash
git init -b main && git add -A
git commit -m "G-KIC-NST Partnering Day 2026 landing page"
git remote add origin https://github.com/Moonhyeong/hbpb1-007-gkic2026.git
git push -u origin main
```

Then: **Settings → Pages → Source: `main` / `/ (root)`**. `.nojekyll` is present so asset paths are
served as-is.

## Regenerating

- Page: `../gkic-partnering-2026/build_landing.py` (copies the sibling page, swaps event branding)
- QR: `qr/generate_qr.py`
- Supporting material PDF: `../gkic-partnering-2026/make_onepager.py`
