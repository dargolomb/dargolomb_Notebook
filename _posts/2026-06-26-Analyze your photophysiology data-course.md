# Photophysiology of Intertidal Macroalgae
### Dar Golomb | Research Methods 2026 | University of Haifa

---

## Table of Contents
1. [Introduction](#introduction)
2. [Materials and Methods](#materials-and-methods)
3. [Results](#results)
4. [Interpretation](#interpretation)
5. [Repository Contents](#repository-contents)

---

## Introduction

Photoacclimation is the physiological adjustment of photosynthetic machinery in response to prevailing light conditions. Intertidal macroalgae experience highly variable light environments — from intense solar irradiance during low tide to darkness during high tide and nocturnal periods. Algae collected from light-exposed positions are expected to display a "sun-type" photophysiology (high light-saturation irradiance Ik, low apparent quantum yield AQY), while dark-acclimated algae should display a "shade-type" physiology (low Ik, high AQY).

This study measured Photosynthesis–Irradiance (PI) curves of 13 light-acclimated and 8 dark-acclimated macroalgal samples from a rocky intertidal site on the Israeli Mediterranean coast (collected 16 April 2026). Non-linear least squares fitting was used to extract photophysiological parameters, and a paired Wilcoxon signed-rank test compared light- and dark-acclimated states across six matched taxa.

---

## Materials and Methods

### Sample collection
Intertidal macroalgae were collected from a rocky shore on **16 April 2026**. Thirteen species were sampled for the light-acclimated (Light) group and eight species for the dark-acclimated (Dark) group. Light-acclimated samples were measured under ambient field light; dark-acclimated samples were dark-adapted for ≥15 minutes prior to measurement.

### PAM fluorometry
PI curves were recorded using a **Walz Water-PAM II** pulse amplitude modulation fluorometer across **17 PAR steps** (0–701 µmol photons m⁻² s⁻¹). At each step, the following were recorded per sample: steady-state fluorescence (F), maximum fluorescence (Fm′), minimum fluorescence (Fo′), effective quantum yield Y(II), non-photochemical quenching yield Y(NPQ), and electron transport rate (ETR).

### Derived parameters

| Parameter | Description | Units |
|-----------|-------------|-------|
| **ETRmax** | Maximum recorded ETR (light group) | µmol electrons m⁻² s⁻¹ |
| **Fv/Fm** | Maximum quantum yield of PSII at PAR = 0 | dimensionless |
| **NPQmax** | Peak Y(NPQ) across all PAR steps | dimensionless |
| **NPQ\_auc** | Area under Y(NPQ)–PAR curve (trapezoidal) | µmol photons m⁻² |

### PI curve model
NLS fitting used the Webb–Falkowski model:

$$\text{ETR} = A_m \cdot \frac{\alpha \cdot \text{PAR}}{\sqrt{A_m^2 + (\alpha \cdot \text{PAR})^2}} - R_d$$

Fitted parameters: **Am** (max ETR), **AQY / α** (initial slope), **Rd** (dark respiration), **Ik = Am / AQY** (saturation irradiance). PAR > 600 and zero ETR values at PAR > 0 were excluded. Samples Light\_3 (*Nemalion*) and Light\_9 (*Halimeda*) were excluded due to poor curve quality.

### Statistics
Paired Wilcoxon signed-rank tests compared Light vs Dark for each parameter across the 7 taxa measured in both groups. P-values were BH-corrected (α = 0.05). A secondary analysis excluded *Colpomenia* (n = 6).

### Software
Python 3.10.12 — `pandas` 2.3.3, `numpy` 2.2.6, `scipy` 1.15.3, `matplotlib` 3.10.9, `statsmodels` ≥0.14.
Analysis script: [`photophysiology_analysis.py`](photophysiology_analysis.py)

---

## Results

### Sample metadata

| Sample\_ID | Taxon | Group | Used in analysis |
|------------|-------|-------|-----------------|
| Light\_1 | *Jania* | Light | ✓ paired |
| Light\_2 | *Halopteris* | Light | excluded (no dark pair) |
| Light\_3 | *Nemalion* | Light | excluded (poor curve) |
| Light\_4 | *Padina* | Light | ✓ paired |
| Light\_5 | *Hypnea* | Light | excluded (no dark pair) |
| Light\_6 | *Codium* | Light | excluded (no dark pair) |
| Light\_7 | *Laurencia* | Light | ✓ paired |
| Light\_8 | *Cystoseira* | Light | excluded (no dark pair) |
| Light\_9 | *Halimeda* | Light | excluded (poor curve) |
| Light\_10 | *Galaxaura* | Light | excluded (no dark pair) |
| Light\_11 | *Colpomenia* | Light | ✓ paired |
| Light\_12 | *Ulva* | Light | ✓ paired |
| Light\_13 | *Dictyota* | Light | ✓ paired |
| Dark\_1 | *Jania* | Dark | ✓ paired |
| Dark\_2 | *Padina* | Dark | ✓ paired |
| Dark\_3 | *Laurencia* | Dark | ✓ paired |
| Dark\_4 | *Colpomenia* | Dark | ✓ paired |
| Dark\_5 | *Ulva* | Dark | ✓ paired |
| Dark\_6 | Red\_UNK | Dark | excluded (no light pair) |
| Dark\_7 | *Dictyota* | Dark | ✓ paired |
| Dark\_8 | *Galaxaura* | Dark | excluded (no light pair) |

---

### PI curves

**Figure 1.** Raw ETR–PAR curves for all light-acclimated samples before filtering. Some samples reach ETR = 0 at high PAR (measurement end); these values were treated as NA.

![Fig1 – Light raw curves](Fig1_light_raw.png)

---

**Figure 2.** Fitted PI curves for light-acclimated algae (n = 11). Points = measured ETR; lines = NLS model fit.

![Fig2 – PI curves light](Fig2_PI_curves_light.png)

---

**Figure 3.** Raw ETR–PAR curves for dark-acclimated samples (all 8 yielded complete curves).

![Fig3 – Dark raw curves](Fig3_dark_raw.png)

---

**Figure 4.** Fitted PI curves for dark-acclimated algae (n = 8).

![Fig4 – PI curves dark](Fig4_PI_curves_dark.png)

---

**Figure 5.** Combined PI curves — light-acclimated (left) and dark-acclimated (right) on a common scale.

![Fig5 – PI curves combined](Fig5_PI_curves_combined.png)

---

### NLS parameters — summary statistics

**Table 1.** Descriptive statistics of NLS-fitted parameters for Light and Dark groups.

| Parameter | Group | n | Mean | SD | Min | Median | Max |
|-----------|-------|---|------|----|-----|--------|-----|
| Am (µmol e⁻ m⁻² s⁻¹) | Light | 11 | 21.62 | 12.81 | 6.55 | 17.79 | 47.29 |
| Am | Dark | 8 | 18.16 | 12.69 | 5.98 | 15.00 | 40.57 |
| AQY | Light | 11 | 0.140 | 0.025 | 0.100 | 0.139 | 0.191 |
| AQY | Dark | 8 | 0.192 | 0.072 | 0.071 | 0.208 | 0.308 |
| Rd (µmol e⁻ m⁻² s⁻¹) | Light | 11 | 0.022 | 0.043 | 0.000 | 0.000 | 0.136 |
| Rd | Dark | 8 | 0.084 | 0.105 | 0.000 | 0.048 | 0.252 |
| Ik (µmol photons m⁻² s⁻¹) | Light | 11 | 150.4 | 74.8 | 56.0 | 143.2 | 259.2 |
| Ik | Dark | 8 | 102.5 | 60.3 | 24.8 | 120.4 | 188.6 |

---

### Distribution of parameters

**Figure 6.** QQ plots of Am, AQY, Rd, and Ik for Light (top) and Dark (bottom) groups. Most parameters — especially Rd — deviate from normality, supporting the use of non-parametric tests.

![Fig6 – QQ plots](Fig6_QQ_plots.png)

---

**Figure 7.** Boxplots of all four parameters for both groups, with individual data points coloured by taxon (all 19 successfully fitted samples).

![Fig7 – Boxplots all taxa](Fig7_boxplots_by_group.png)

---

**Figure 8.** Boxplots restricted to the 7 paired taxa (those present in both groups), coloured by taxon.

![Fig8 – Boxplots paired taxa](Fig8_boxplots_paired_taxa.png)

---

### Light vs Dark comparison

**Figure 9.** Difference (Light − Dark) in each parameter per taxon. Positive bars = higher in light-acclimated state.

![Fig9 – Difference](Fig9_difference_plot.png)

---

**Figure 10.** Ratio (Light / Dark) per parameter. Dashed red line = ratio of 1 (no difference). Ratios > 1 indicate the light group exceeded the dark group.

![Fig10 – Ratio](Fig10_ratio_plot.png)

---

**Figure 11.** Combined summary of differences (top row) and ratios (bottom row) for all four parameters across paired taxa.

![Fig11 – Diff and ratio combined](Fig11_diff_ratio_combined.png)

---

### Statistical tests

**Table 2.** Paired Wilcoxon signed-rank tests comparing Light vs Dark across 7 paired taxa. P-values adjusted by the Benjamini–Hochberg method.

| Parameter | p-value | p\_adj (BH) | Significant? |
|-----------|---------|-------------|--------------|
| Am | 0.6875 | 0.6875 | No |
| AQY | 0.1094 | 0.1667 | No |
| Rd | 0.1250 | 0.1667 | No |
| Ik | 0.0781 | 0.1667 | No |

A secondary analysis excluding *Colpomenia* (n = 6) yielded the same conclusions (all p\_adj ≥ 0.33; see `paired_wilcoxon_no_Colpomenia.csv`).

---

## Interpretation

### What do the parameters tell us?

**Am (maximum ETR):** Reflects maximum photosynthetic capacity (analogous to Pmax). The wide spread across species (Light: 6.5–47.3 µmol e⁻ m⁻² s⁻¹) reflects the taxonomic diversity sampled. *Laurencia* had the highest Am in the light group (47.3), suggesting high photosynthetic performance under natural irradiance. Mean Am was slightly higher in the light group (21.6 vs 18.2), but the difference was not significant.

**AQY (apparent quantum yield / α):** The initial slope of the PI curve — efficiency at sub-saturating light. AQY was on average **higher in dark-acclimated algae** (0.192 vs 0.140). This matches classical photoacclimation theory: shade- or dark-acclimated organisms expand their light-harvesting antennae to capture more photons at low irradiance, increasing the initial slope. Light-adapted organisms downregulate antennae to protect against photodamage, reducing AQY.

**Rd (dark respiration):** The y-intercept of the PI curve. Values were near zero for most samples. Dark-acclimated algae showed slightly higher Rd (mean 0.084 vs 0.022), possibly reflecting greater metabolic maintenance costs in the absence of photosynthetic production.

**Ik (saturation irradiance):** The PAR at which photosynthesis transitions from light-limited to saturated. Light-acclimated algae had a **higher mean Ik** (150.4 vs 102.5 µmol photons m⁻² s⁻¹), consistent with a "sun-adapted" physiology requiring more light to reach saturation. This was the parameter closest to significance (p = 0.078 before correction).

### Why were no differences statistically significant?

Despite biologically sensible trends in AQY and Ik, no parameter reached significance (all p\_adj > 0.05). Three explanations are likely:

1. **Low sample size** — with only n = 7 paired taxa, the Wilcoxon test has limited statistical power. The Ik result (p = 0.078) hints at a real trend that a larger dataset might detect.
2. **High inter-species variability** — the 7 taxa differ greatly in morphology, ecology, and photosynthetic strategy. This variance overwhelms the within-species acclimation signal.
3. ***Colpomenia* as an outlier** — *Colpomenia* showed higher Am in the Dark group (40.6) than the Light group (31.2), the opposite of the general trend, potentially reducing the test's ability to detect a consistent direction.

### Ecological conclusion

The data are **broadly consistent with expected photoacclimation responses**: light-acclimated algae tended towards higher Ik (sun physiology) and dark-acclimated algae towards higher AQY (shade physiology). The lack of statistical significance reflects the small, diverse sample rather than an absence of the biological phenomenon. Future work should sample multiple individuals of the same species from contrasting microhabitats and control for tidal exposure history.

---

## Repository Contents

| File | Description |
|------|-------------|
| `light.csv` | Raw PAM data — light-acclimated group |
| `dark.csv` | Raw PAM data — dark-acclimated group |
| `Photophysiology_metadata.csv` | Sample ID, taxon, and group assignments |
| `Photophysiology_Dar_Golomb_2026.csv` | Organized parameter data (Mock format) ★ |
| `Photophysiology_Dar_Golomb_2026.xlsx` | Same data as Excel with ReadMe tab ★ |
| `photophysiology_analysis.py` | Full analysis script ★ |
| `R_environment_versions.json` | Software environment ★ |
| `light_group_photo_parameters.csv` | NLS parameters — light group |
| `dark_group_photo_parameters.csv` | NLS parameters — dark group |
| `Photophysiology_summary_table.csv` | Descriptive statistics table |
| `diff_ratio_by_taxon.csv` | Light vs Dark differences and ratios |
| `paired_wilcoxon_test.csv` | Statistical test results |
| `paired_wilcoxon_no_Colpomenia.csv` | Test results excluding *Colpomenia* |
| `Fig1_light_raw.png` – `Fig11_diff_ratio_combined.png` | All figures |
| `Materials_and_Methods.md` | Full M&M report ★ |
| `Results_and_Interpretation.md` | Results + Interpretation ★ |
| `R.R` | Original R script provided for the course |

★ = submitted deliverable

---

*Dar Golomb · University of Haifa · Research Methods 2026*
