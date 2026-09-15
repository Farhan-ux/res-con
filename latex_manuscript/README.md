# Entropy-Gated Contrastive Decoding — LaTeX Manuscript

This folder contains the LaTeX source of the manuscript **"Entropy-Gated Contrastive Decoding: Mitigating Visual Inertia and Multimodal Hallucinations in Vision-Language Models"**, formatted with the official Springer Nature LaTeX template (`sn-jnl` v3.1, December 2024) for submission to **Applied Intelligence** (Springer, journal code 10489).

## Folder contents

| File | Description |
|------|-------------|
| `sn-article.tex` | Main LaTeX source — single self-contained `.tex` file |
| `references.bib` | BibTeX bibliography (45 entries, all cited) |
| `sn-jnl.cls` | Springer Nature journal class file (v3.1, Dec 2024) |
| `sn-basic.bst` | Basic Springer Nature bibliography style (numbered) |
| `fig1.png` … `fig9.png` | Figure images (extracted from the original draft) |
| `sn-article.pdf` | Compiled PDF (20 pages, generated with pdflatex + bibtex) |
| `README.md` | This file |

## Journal formatting choices (Applied Intelligence, 10489)

- **Document class:** `\documentclass[pdflatex,sn-basic,Numbered]{sn-jnl}`
  - `sn-basic` → Basic Springer Nature reference style
  - `Numbered` → numbered in-text citations `[1]`, `[2]`, `[1–3]`, references listed in order of citation
- **Abstract:** within the 150–250 word window required by the journal
- **Keywords:** 5 keywords (journal accepts 4–6)
- **Headings:** decimal section numbering (1, 1.1, 1.1.1), three levels max
- **Declarations section:** included with all mandatory items (Funding, Competing interests, Ethics, Consent, Data/Materials/Code availability, Author contribution)

## How to compile

```bash
pdflatex sn-article
bibtex   sn-article
pdflatex sn-article
pdflatex sn-article
```

The expected output is `sn-article.pdf` (≈ 20 pages, single column, peer-review layout).

## Notes

- The author block in `sn-article.tex` uses placeholder names (`First Author`, `Second Author`, `Third Author`) and a placeholder affiliation. Replace these with the actual author list before submission.
- All nine figures are kept as PNG files in the same folder as the `.tex` (per the Springer Nature submission requirement that image files live alongside the `.tex`, not in subfolders).
- Equations are typeset with `amsmath` (`equation` and `align` environments). Algorithm 1 uses the `algorithm` + `algpseudocode` packages.
- Tables use `booktabs` (`\toprule`, `\midrule`, `\botrule`). The wide threshold-sweep table (Table A1) is set as a `sidewaystable` for legibility.
