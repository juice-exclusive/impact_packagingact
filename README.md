# Replication: Reusable Packaging Mandates Increase Availability but Not Consumer Usage

[Authors anonymized for peer review] (2025).  
*Nature Sustainability.*

---

## Requirements

- R >= 4.2
- Quarto >= 1.4
- Packages are loaded automatically via `pacman::p_load()` in each notebook

---

## Reproduce

Run notebooks in this order from the project root:

```bash
quarto render notebooks/d_02_data_exploration_II.qmd   # supply-side maps (fig-map)
quarto render notebooks/d_03_analysis_ITSA_II.qmd      # ITSA main results (fig-plot-mean, tbl-itsa-main)
quarto render notebooks/u_03_analysis_nuts3_II.qmd     # DiD event study (fig-event-study)
quarto render notebooks/u_03_analysis_stores_II.qmd    # cohort analysis (tbl-cohort-full1)
quarto render notebooks/u_04_mechanism_fig.qmd         # mechanism figure (fig-mechanism-4panel)
```

Precomputed model objects in `assets/objects/` allow rendering the notebooks directly without re-estimating models.

---

## Data

| File | Description |
|---|---|
| `data/processed/model2_data.RData` | Monthly NUTS-3 supply panel, 394 German regions, March 2021–December 2024 |
| `data/u_processed/monthly_panel_nuts3_AT_DE_FR.RData` | Monthly NUTS-3 transaction panel, DE + AT, 181 regions |
| `data/u_processed/monthly_panel_stores_AT_DE_FR.RData` | Store-level transaction panel (anonymized — restaurant names and addresses removed) |

**Raw data not included:**

- Raw transaction data (Vytal GmbH): available on reasonable request from Vytal (vytal.org)
- Restaurant network data: scraped from provider websites (see Methods)
- Demographic covariates: available from GfK SE under commercial license (gfk.com)

---

## License

Code: CC BY 4.0. Data: see Data availability statement in the manuscript.
