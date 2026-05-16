<img width="3600" height="2400" alt="Figure_1_Response_curves_matched_algae_only" src="https://github.com/user-attachments/assets/454c18c7-41bc-4a92-bb22-4cc43688902c" />
# Photophysiological Responses of Macroalgae Under Light and Dark Treatments

**Author:** Dar Golomb  
**Course:** Research Methods 2026  
**Project:** Photophysiology mock dataset  

---

## Overview

This project analyzes photophysiological responses of macroalgae measured under **light** and **dark** treatments. The dataset includes fluorescence-based parameters measured across a gradient of photosynthetically active radiation (PAR). The aim was to organize the raw data, assign algae identities to each sample, visualize response curves, and statistically compare light and dark treatments.

The raw data were provided in two files:

- `dark.csv`
- `light.csv`

The data were cleaned, reshaped from wide to long format, matched by algae identity, and analyzed in R.

---

## Data Cleaning and Organization

The original files contained repeated measurements for several photophysiological parameters across a PAR gradient. Each sample was manually assigned to its algae identity according to the measurement order.

One sample was removed before analysis:

| Treatment | Sample | Algae | Reason |
|---|---:|---|---|
| Light | 9 | Ulva | Removed because the measurements were not reliable |

To allow a direct comparison between treatments, only algae that were present in **both** the light and dark treatments were retained for the final analysis.

The final matched dataset included seven algae identities:

- Colpomenia
- Dictyota
- Galaxaura
- Jania
- Padina
- Sargassum
- Ulva

---

## Parameters Analyzed

The following photophysiological parameters were analyzed:

| Parameter | Meaning | Unit |
|---|---|---|
| F | Fluorescence yield | Relative fluorescence units |
| Fm' | Maximum fluorescence under light-adapted conditions | Relative fluorescence units |
| Fo' | Minimum fluorescence under light-adapted conditions | Relative fluorescence units |
| Y(II) | Effective quantum yield of photosystem II | Unitless |
| Y(NPQ) | Regulated non-photochemical energy dissipation | Unitless |
| ETR | Electron transport rate | Relative units unless instrument-calibrated |
| PAR | Photosynthetically active radiation | µmol photons m⁻² s⁻¹ |

---

## Statistical Approach

Because each sample was measured repeatedly across multiple PAR levels, individual PAR measurements were not treated as fully independent observations. Instead, curve-level metrics were calculated for each sample and parameter.

The main curve-level metrics were:

- Area under the curve (AUC)
- Maximum value
- PAR at maximum value
- Value at PAR 0
- Value at PAR 701

The main statistical comparison between light and dark treatments was based on **AUC**, which summarizes the full response curve for each sample.

Normality was assessed using the Shapiro–Wilk test. Homogeneity of variance was assessed using Levene’s test. Depending on the assumptions, either Welch’s t-test or the Mann–Whitney U test was applied.

All analyses were performed in R using the following packages:

- `dplyr`
- `tidyr`
- `purrr`
- `broom`
- `rstatix`
- `ggplot2`
- `writexl`

---

## Results

After removing Light sample 9 and retaining only algae that were present in both treatments, the final analysis included seven matched algae identities in each treatment group.

For each photophysiological parameter, AUC was calculated across the PAR gradient and compared between light and dark treatments. No statistically significant differences were detected between treatments for any of the measured parameters.

### AUC comparison between light and dark treatments

| Parameter | n Dark | n Light | Statistical test | p-value | Interpretation |
|---|---:|---:|---|---:|---|
| ETR | 7 | 7 | Welch t-test | 0.403 | Not significant |
| F | 7 | 7 | Welch t-test | 0.399 | Not significant |
| Fm' | 7 | 7 | Welch t-test | 0.407 | Not significant |
| Fo' | 7 | 7 | Welch t-test | 0.743 | Not significant |
| Y(II) | 7 | 7 | Welch t-test | 0.621 | Not significant |
| Y(NPQ) | 7 | 7 | Welch t-test | 0.785 | Not significant |

Overall, the statistical analysis did not provide evidence for a significant treatment effect between light and dark conditions in the matched algae dataset.

---

## Figures

### Figure 1. Mean photophysiological response curves

This figure shows mean photophysiological response curves across the PAR gradient for each parameter in the matched algae dataset.

<img width="3600" height="2400" alt="Figure_1_Response_curves_matched_algae_only" src="https://github.com/user-attachments/assets/906ce085-cbfd-4712-aefa-534eb678d3b0" />


### Figure 2. Response curves by algae identity

This figure shows response curves separated by algae identity, allowing visual comparison of species-specific response patterns across the PAR gradient.

<img width="4800" height="3600" alt="Figure_2_Response_curves_by_algae_matched_only" src="https://github.com/user-attachments/assets/10080830-b381-4e53-95ee-8579497b58b0" />


### Figure 3. AUC comparison between light and dark treatments

This figure shows the area under the curve comparison between light and dark treatments for each photophysiological parameter.

<img width="3600" height="2400" alt="Figure_5_AUC_boxplots_matched_algae_only" src="https://github.com/user-attachments/assets/3a7b5e3a-e4c6-43a1-bd8e-b76c9fbb4b12" />


### Figure 4. AUC comparison by algae identity

This figure shows AUC values separated by algae identity and photophysiological parameter.

<img width="4800" height="3600" alt="Figure_6_AUC_boxplots_by_algae_matched_only" src="https://github.com/user-attachments/assets/0905044b-0843-4367-b676-1d027b60c84f" />


---

## Interpretation

The results suggest that, within this dataset, photophysiological responses were not significantly different between algae measured under light and dark treatments. This may indicate that the treatment effect was weak, that variability among algae was high, or that the number of matched samples was too small to detect statistically significant differences.

Restricting the analysis to algae present in both treatments allowed a more appropriate comparison between light and dark conditions. However, this also reduced the final sample size, so the absence of significant differences should be interpreted cautiously.

Using curve-level metrics such as AUC was important because each sample was measured repeatedly across the PAR gradient. Treating each PAR measurement as an independent observation would artificially inflate the sample size. The AUC approach summarizes the entire response curve for each sample and provides a more conservative comparison between treatments.

Although the statistical tests were not significant, the response-curve plots are still useful for visual interpretation. They show how parameters such as ETR, Y(II), and Y(NPQ) change across increasing PAR levels and whether individual algae show different response patterns.

---

## Repository Contents

The full project folder includes:

```text
Dar_Golomb_Photophysiology_homework/

├── README.md
├── R_exercise_photophysiology_2026_Dar_Golomb.R
├── Photophysiology_full_results_MATCHED_ALGAE_with_ReadMe.xlsx
├── Photophysiology_clean_long_format_MATCHED_ALGAE_ONLY.csv
├── Photophysiology_R_environment_MATCHED_ALGAE.RData
├── R_session_info.txt
├── Removed_bad_sample.csv
├── Excluded_unmatched_algae.csv
├── Algae_presence_by_treatment.csv
├── plots/
└── tables/
```

---

## Reproducibility

To reproduce the analysis, run the R script:

```r
source("R_exercise_photophysiology_2026_Dar_Golomb.R")
```

The script imports the raw data, cleans and reshapes the dataset, assigns algae identities, removes the unreliable sample, keeps only algae represented in both treatments, generates summary tables, performs statistical analyses, creates figures, and exports the full results.
