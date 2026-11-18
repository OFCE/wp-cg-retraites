# To check: LaTeX to IFE working paper (Quarto) conversion

Source: `tex/BGGH_v6.tex`. Output: `index.qmd`, `annexes.qmd`, `references.bib`, `figures/`.

## Content to verify

- [ ] Appendix figures "Fiscal consolidation", "Google Trends" (uncertainty) and "Spillovers": the panel captioned "Consumption (%GDP)" uses `*_lnrCons.png`, the same image as the previous panel. `*_cons_GDP.png` exists in `tex/figures/`. Kept as in the tex source. Decide whether to switch to `*_cons_GDP.png`.
- [ ] Fix the filename case in Overleaf: the tex references `dF_Capi_Finv_GDP_SOut.png`, the file is `dF_Capi_finv_GDP_SOut.png`. The qmd already uses the real name.
- [ ] Read the 84 review comments kept as `<!-- -->` in `index.qmd` and `annexes.qmd` (from Carl, JH and TG; TODOs; struck-through text). Resolve them or delete them. This includes the large commented-out paragraphs in Section 2.
- [ ] The tex prose hard-codes section numbers in the roadmap ("Section 2 ...", "Section 7 concludes"). Check they still match the Quarto numbering (7 sections, currently consistent).
- [ ] Check the `econo-mies` hyphenation artifact was fixed everywhere, and look for similar artifacts in the text.
- [ ] 9 bib entries are never cited: `beetsma_what_2020`, `biPublicPensionReforms2023`, `Chetty2012`, `CoileLevine2011`, `GruberWise2004`, `ramey_identifying_2009`, `romer_macroeconomic_2010`, `romerTransferPaymentsMacroeconomy2016`, `rompOECDPensionReform2023`. Keep, cite or prune.
- [ ] Read the full PDF and HTML end to end (callouts for the testable implications, long figure notes, footnotes).

## Layout and style

- [ ] Citation style: `www/csl/apa-6th-edition.csl` was chosen as the closest match to `apalike2`. Confirm or pick another CSL.
- [ ] Table 1 (expected effects): narrow justified columns in the PDF. Tune the column widths if needed.
- [ ] Appendix figures are numbered 1-4 on the annex page, not A.1-A.4. Main-text links read "Appendix Figure k".
- [ ] The extension's `nbsp` filter is French-oriented and runs on English text. Check the PDF for stray thin spaces before `: ; ! ? %`.
- [ ] `fig-notes` divs (figure notes) have no custom styling.

## Branding and metadata

- [ ] The navbar, `site-url`, navbar logo (`www/ifeofce.png`) and the title-page contact block still say OFCE. Only the logo and citation wording follow `institut: ife`. Decide whether to change them.
- [ ] `citation.container-title` is set to "Institut français d'économie working paper". Confirm the wording.
- [ ] Draft mode: `draft: true`, `version: v0`, no `wp:` number, year or stable URL. Fill these in when the paper is registered.
- [ ] Check the author affiliations and the corresponding author flag (Héricourt) in `_quarto.yml`.
- [ ] `date` is set to 2026-11-18. Update it at publication.

## Housekeeping

- [ ] `tex/` is untouched. Decide whether to archive it once the qmd is validated.
- [ ] `figures/` holds 117 PNGs copied from `tex/figures/`. The other ~40 files and `tex/Old_figures/` are not used.
- [ ] Untracked: `_site/`, `.quarto/`, `_extensions/`, `.github/`. Check `.gitignore` before committing.
- [ ] The converter scripts live only in the scratch folder (`/tmp/pa-501/.../conv`). Save them to the repo if you want to re-run the conversion after further tex edits.
