# qPCR Gene Selection for Studying Coral Aggression Stress in *Acropora*

## Background

Coral aggression is a well-documented ecological phenomenon in which one coral physically attacks a neighboring coral using mesenterial filaments or nematocysts. When an *Acropora* coral is targeted by an aggressor coral, nematocysts deliver venom directly into its tissue, causing localized cell damage and triggering both cellular stress and innate immune responses. This experiment aims to investigate how *Acropora* modulates gene expression at the molecular level in response to such biotic stress.

---

## Experimental Setup

- **Organism:** *Acropora* sp.
- **Stress condition:** Inter-coral aggression via nematocyst discharge from an attacking neighboring coral
- **Method:** qPCR-based relative quantification of target gene expression in attacked vs. undisturbed *Acropora* colonies

---

## Target Genes

### Gene 1: NF-κB (Nuclear Factor kappa B)

**Why this gene?**
NF-κB is the primary gene of interest in this experiment. It encodes a transcription factor that acts as a master regulator of the innate immune response in cnidarians, including corals. It is the most specific and informative gene to examine in the context of biotic stress, as it is activated in response to pathogen-associated signals and tissue injury — both of which are triggered by nematocyst envenomation.

**Biological function:**
NF-κB controls the transcription of numerous downstream immune and inflammatory genes. In cnidarians, it has been shown to be activated in response to microbial challenge and tissue damage. When the coral tissue is pierced and envenomated by nematocysts from an aggressor coral, damage-associated molecular patterns (DAMPs) and potentially foreign molecules are released, which are expected to activate the NF-κB signaling pathway.

**Expected expression change:**
Upregulation in attacked *Acropora* compared to undisturbed controls. The degree of upregulation may reflect the intensity and duration of the attack.

**Why relevant to this condition?**
Unlike HSP70, which responds to a broad range of stressors (thermal, osmotic, mechanical), NF-κB is specifically associated with immune activation. Its upregulation in response to nematocyst attack would confirm that the coral mounts a targeted immune-type response — not merely a generic cellular stress reaction.

---

### Gene 2: HSP70 (Heat Shock Protein 70)

**Why this gene?**
HSP70 is one of the most extensively studied stress-response genes in corals. It encodes a molecular chaperone that assists in the refolding of damaged proteins and prevents protein aggregation under cellular stress conditions. While it is not immune-specific, examining it alongside NF-κB allows us to distinguish between a generalized cellular stress response and a targeted immune reaction.

**Biological function:**
HSP70 is a member of the heat shock protein family and is upregulated whenever cellular proteostasis is disrupted — by heat, toxins, or mechanical injury. Nematocyst venom contains cytolytic peptides and enzymes (e.g., phospholipases) that cause direct protein and membrane damage, which would be expected to trigger HSP70 expression in affected cells.

**Expected expression change:**
Upregulation in attacked *Acropora* tissue, particularly at the site of contact. We expect both NF-κB and HSP70 to be upregulated, but hypothesize that NF-κB will show a more pronounced response relative to baseline, reflecting a stronger immune-specific signal.

**Why relevant to this condition?**
Nematocyst venom is directly cytotoxic. HSP70 upregulation would indicate that affected cells are experiencing proteotoxic stress and actively attempting to recover. This makes it a useful complementary marker alongside the immune-specific NF-κB signal.

---

### Gene 3: Caspase-3

**Why this gene?**
Caspase-3 is the key executioner of the apoptosis pathway. In the context of nematocyst envenomation, cells that cannot repair the toxin-induced damage may undergo programmed cell death. Including Caspase-3 allows us to evaluate whether the tissue response goes beyond stress and immune activation into irreversible cell death — which would reflect the severity of the attack.

**Biological function:**
Caspase-3 is an intracellular protease activated in the final stages of the intrinsic apoptotic pathway. In corals, apoptosis is known to play a role in bleaching and tissue loss. Following nematocyst attack, heavily damaged cells at the contact zone may activate apoptosis as a containment strategy.

**Expected expression change:**
A moderate or localized upregulation is expected at the site of attack. Systemic upregulation would indicate more widespread tissue compromise. If the attack is sub-lethal, Caspase-3 levels may not change significantly, making it a useful indicator of attack severity.

**Why relevant to this condition?**
The apoptotic response places the immune and stress responses in a functional context: is the coral coping and repairing, or are cells being lost? Caspase-3 adds a third dimension to the molecular picture alongside NF-κB and HSP70.

---

## Reference Gene: EF1α (Elongation Factor 1-alpha)

**Why EF1α?**
EF1α encodes a core translation elongation factor involved in the delivery of aminoacyl-tRNA to the ribosome. It is constitutively expressed at high and stable levels across tissues and conditions, making it a widely validated reference gene for qPCR normalization in *Acropora* and other coral species.

**Why expect stable expression under aggression stress?**
Unlike HSP70 or actin (which can shift under stress), EF1α expression has been shown to remain stable under a range of biotic and abiotic perturbations in cnidarians, including immune challenge and moderate mechanical stress. Nematocyst-induced local tissue injury is not expected to alter global translation rates in the coral holobiont at the whole-colony level, which is the tissue used for RNA extraction.

**Supporting rationale:**
EF1α has been validated as a reference gene in multiple *Acropora* qPCR studies (e.g., studies on thermal stress, bleaching, and immune response), reinforcing its appropriateness for this experimental context.

---

## Summary Table

| Gene | Type | Expected Change | Rationale |
|------|------|----------------|-----------|
| NF-κB | Target (primary) | Upregulated | Immune-specific transcription factor; activated by nematocyst venom |
| HSP70 | Target (secondary) | Upregulated | General cellular stress; protein damage from venom |
| Caspase-3 | Target (tertiary) | Moderate upregulation | Apoptosis marker; reflects severity of cell damage |
| EF1α | Reference | Stable | Constitutive expression; validated in *Acropora* qPCR studies |

---

## Hypotheses Summary

We hypothesize that *Acropora* colonies subjected to nematocyst attack from an aggressor coral will show significant upregulation of NF-κB and HSP70, reflecting concurrent immune activation and cellular stress. Caspase-3 upregulation, if observed, would indicate that the level of tissue damage exceeded the coral's repair capacity. The relative magnitude of NF-κB versus HSP70 expression will help distinguish whether the dominant response is immune-specific or a generalized stress reaction.
