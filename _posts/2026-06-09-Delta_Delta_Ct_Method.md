# Interpreting qPCR Data: The Delta-Delta Ct (ΔΔCt) Method

## What is qPCR Relative Quantification?

In qPCR experiments, we measure gene expression by tracking how many cycles it takes for a fluorescent signal to cross a detection threshold. This value is called the **Cycle Threshold (Ct)**. A lower Ct means more starting material — the gene was expressed at a higher level in that sample.

Relative quantification allows us to compare gene expression between two conditions **without knowing the absolute amount of RNA**. Instead, we normalize to a reference (housekeeping) gene and compare across conditions. The standard method for this is the **ΔΔCt method**.

---

## The ΔΔCt Method — Step by Step

### Step 1: Calculate ΔCt (Delta Ct)

For each gene in each condition, subtract the Ct of the **reference gene** from the Ct of the **target gene**:

$$\Delta Ct = Ct_{target} - Ct_{reference}$$

This normalization removes variation due to differences in the amount of RNA loaded.

### Step 2: Calculate ΔΔCt (Delta-Delta Ct)

Subtract the ΔCt of the **control group** from the ΔCt of the **treatment group**:

$$\Delta\Delta Ct = \Delta Ct_{treatment} - \Delta Ct_{control}$$

This tells us how much the gene's expression changed relative to the control.

### Step 3: Calculate Fold Change

Convert the ΔΔCt value into a **fold change**:

$$\text{Fold Change} = 2^{-\Delta\Delta Ct}$$

- **Fold Change > 1** → gene is **upregulated** in the treatment
- **Fold Change < 1** → gene is **downregulated** in the treatment
- **Fold Change = 1** → no change in expression

---

## Class Data: Inhibitor Treatment vs. DMSO Control

**Reference gene:** Tubulin  
**Control:** DMSO  
**Treatment:** Inhibitor

### Raw Ct Values

| Gene | Ct (Control) | Ct (Treatment) |
|------|-------------|----------------|
| Tubulin | 23.2956 | 23.2956 |
| ascs | 29.0941 | 28.5087 |
| Delta | 25.9637 | 25.5380 |
| ets | 24.7168 | 24.4373 |
| foxA | 24.3659 | 23.7225 |
| gcm | 28.3543 | 28.1783 |
| NGN | 28.3512 | 27.3529 |
| opt | 31.0205 | 31.7082 |
| pak3 | 25.4058 | 25.2948 |
| pak4 | 25.5711 | 25.2525 |
| pitx | 29.6782 | 31.7242 |
| SM30 | 20.9688 | 21.7664 |
| sm50 | 23.7002 | 24.8107 |
| soxC | 25.0721 | 24.3279 |
| synB | 24.1262 | 24.0595 |

---

### Calculations

| Gene | ΔCt (Control) | ΔCt (Treatment) | ΔΔCt | Fold Change |
|------|--------------|----------------|------|-------------|
| ascs | 5.7985 | 5.2131 | −0.5854 | **1.500** |
| Delta | 2.6681 | 2.2424 | −0.4257 | **1.343** |
| ets | 1.4212 | 1.1418 | −0.2794 | **1.214** |
| foxA | 1.0703 | 0.4269 | −0.6434 | **1.562** |
| gcm | 5.0588 | 4.8827 | −0.1761 | **1.130** |
| NGN | 5.0556 | 4.0574 | −0.9983 | **1.998** |
| opt | 7.7249 | 8.4126 | +0.6877 | **0.621** |
| pak3 | 2.1102 | 1.9992 | −0.1110 | **1.080** |
| pak4 | 2.2756 | 1.9570 | −0.3186 | **1.247** |
| pitx | 6.3826 | 8.4286 | +2.0460 | **0.242** |
| SM30 | −2.3268 | −1.5292 | +0.7976 | **0.575** |
| sm50 | 0.4046 | 1.5152 | +1.1105 | **0.463** |
| soxC | 1.7765 | 1.0323 | −0.7442 | **1.675** |
| synB | 0.8306 | 0.7639 | −0.0667 | **1.047** |

**Example calculation for NGN:**
- ΔCt (Control) = 28.3512 − 23.2956 = 5.0556
- ΔCt (Treatment) = 27.3529 − 23.2956 = 4.0574
- ΔΔCt = 4.0574 − 5.0556 = **−0.9983**
- Fold Change = 2^(−(−0.9983)) = 2^0.9983 = **1.998 ≈ 2.0**

This means NGN expression **doubled** in the inhibitor treatment compared to the control.

---

## Results Graph

![Fold Change Bar Chart](fold_change_chart.png)

*Green bars = upregulated (FC > 1) | Red bars = downregulated (FC < 1) | Dashed line = no change*

---

## Interpretation

### Upregulated genes (FC > 1)
The following genes showed **increased expression** under inhibitor treatment:

| Gene | Fold Change | Interpretation |
|------|-------------|----------------|
| NGN | 1.998 | ~2× upregulated — strongest upregulation |
| soxC | 1.675 | ~1.7× upregulated |
| foxA | 1.562 | ~1.6× upregulated |
| ascs | 1.500 | ~1.5× upregulated |
| Delta | 1.343 | ~1.3× upregulated |
| pak4 | 1.247 | ~1.25× upregulated |
| ets | 1.214 | ~1.2× upregulated |
| gcm | 1.130 | mild upregulation |
| pak3 | 1.080 | minimal change |
| synB | 1.047 | minimal change |

### Downregulated genes (FC < 1)
The following genes showed **decreased expression** under inhibitor treatment:

| Gene | Fold Change | Interpretation |
|------|-------------|----------------|
| pitx | 0.242 | ~4× downregulated — strongest downregulation |
| sm50 | 0.463 | ~2× downregulated |
| SM30 | 0.575 | ~1.7× downregulated |
| opt | 0.621 | ~1.6× downregulated |

### Summary

The inhibitor treatment caused a mixed effect on gene expression. Most transcription factor genes (NGN, soxC, foxA, ascs, Delta) were upregulated, while structural/biomineralization genes (SM30, sm50, pitx, opt) were markedly downregulated. This pattern suggests that the inhibitor disrupts a downstream regulatory pathway — potentially interfering with differentiation or skeletogenesis while leaving or amplifying upstream transcriptional activity. The most dramatic changes were seen in **pitx** (4× down) and **NGN** (2× up), making these the most informative genes for understanding the inhibitor's mechanism of action.
