# EGCD Re-Analysis — Canonical Split

This folder holds the consolidated re-analysis of the EGCD paper after fixing the
canonical split (seed=42, stratified by image) and recomputing all metrics on the
held-out 842-query partition. Replaces the original Table 1 (which mixed full-dataset
and held-out splits).

## Files

| File | Description |
|------|-------------|
| `EGCD_paper_changes.docx` | **Main deliverable.** Word doc with: new Table 1, McNemar results, per-model degradation, 12 numbered number updates, 5 claim-softening edits, 6 notation/implementation fixes, 11 bibliography/proofing fixes, figure swap mapping. |
| `EGCD_reanalysis_consolidated.xlsx` | 14-sheet workbook: README, Table_1_HeldOut, Table_1_OldVsNew, McNemar, TauStar_Selection, Tuning_Sweep (147 rows), Routing_Fraction, and 7 PerItem sheets (842 held-out items × 11 columns each). |
| `egcd_reanalysis.json` | Machine-readable structured results (all metrics + McNemar + sweep data per model). |
| `comparison_summary.txt` | Human-readable old-vs-new comparison printout. |
| `figures/` | 8 figures × 2 formats (PNG 300dpi + PDF), paper-style set (same recipes as `v4/`), regenerated on the canonical-split numbers. |

## Canonical Split

- seed=42
- Stratified by **image id** (not by query) — AMBER has multiple queries per image, so image-level splitting prevents leakage between tuning and held-out.
- Yields: 822 tuning queries + 842 held-out queries.
- Identical across all 14 result files (7 EGCD + 7 VCD/SID).

## McNemar Test

Exact two-sided McNemar on paired per-item correctness, computed from real
discordant-pair counts. Replaces the old paper's infeasible p > 0.99 values
(which couldn't be reproduced from the reported marginals).

## Sources

- `egcd_results/final_entropy_gated_results_<tag>.json` (7 files)
- `vcd_results/egcd_baselines_<tag>.json` + `Qwen2.5-VL-7B_VCD.json` + `llava-v1.6-mistral-7b-vcd.json` (7 files)

## Generated

2026-09-15 (canonical-split re-analysis)
