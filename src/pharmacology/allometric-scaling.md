# Allometric Scaling

## Introduction

Wildlife veterinarians frequently face the challenge of dosing drugs for species in which pharmacokinetic data do not exist. With over 70,000 vertebrate species and pharmacokinetic studies available for only a small fraction, some method of extrapolating doses across species is essential. Allometric scaling provides a physiologically grounded approach to this problem by exploiting the predictable mathematical relationship between body size and metabolic rate across the animal kingdom.

## Principles of Allometric Scaling

### The Body Size–Metabolism Relationship

The fundamental observation underlying allometric scaling is that metabolic rate does not scale linearly with body mass. Instead, it follows a power law:

**Basal Metabolic Rate (BMR) = a x (Body Weight)^b**

Where:
- **a** = a taxon-specific constant (scaling coefficient)
- **Body Weight** = mass in kilograms
- **b** = the scaling exponent (approximately 0.75 for most vertebrates)

This means that smaller animals have a higher metabolic rate per kilogram of body weight than larger animals. A 25-gram mouse has a mass-specific metabolic rate approximately 10 times higher than a 70-kilogram human.

### Metabolic Scaling Exponents

| Taxon | Scaling Exponent (b) | Constant (a) (kcal/day) | Notes |
|---|---|---|---|
| Placental mammals | 0.75 | 70 | Best-studied; the "Kleiber's law" relationship |
| Marsupials | 0.74 | 49 | Lower basal metabolic rate than placentals |
| Passerine birds | 0.72 | 129 | Higher BMR than non-passerines |
| Non-passerine birds | 0.73 | 78 | Intermediate between mammals and passerines |
| Reptiles (at 37°C) | 0.77 | 10 | BMR ~10–20% of mammalian BMR at equivalent temperature |
| Amphibians (at 25°C) | 0.75 | 3 | Very low BMR; temperature-dependent |

### Why 0.75?

The three-quarter power scaling of metabolism with body mass (Kleiber's law) has been observed across taxa from unicellular organisms to whales. Multiple theories have been proposed to explain this relationship:

- **Fractal network model** (West, Brown, Enquist 1997): The geometry of the vascular supply network (a space-filling fractal) constrains nutrient delivery and energy dissipation, producing a 3/4 exponent
- **Surface area model**: Originally proposed as 2/3 (surface area scales as BW^0.67), but empirical data consistently show 0.75 rather than 0.67
- **Multifactorial**: The exponent likely reflects the integrated constraints of heat dissipation, vascular geometry, and organ function across body sizes

The exact value of the exponent remains debated, with some authors arguing for a range of 0.67–0.80 depending on taxon and methodology. For practical drug dosing, **0.75 is the accepted standard**.

## The Allometric Drug Dosing Formula

### Basic Formula

To extrapolate a drug dose from a reference species to a target species:

**Dose_target = Dose_reference x (BW_target / BW_reference)^(1-b)**

Or equivalently, using the minimum energy cost (MEC) approach:

**Dose_target = Dose_reference x (MEC_target / MEC_reference)**

Where:
- **Dose_reference** = known dose in the reference species (mg/kg)
- **BW_target** = body weight of the target species (kg)
- **BW_reference** = body weight of the reference species (kg)
- **b** = scaling exponent (typically 0.75)
- **MEC** = Minimum Energy Cost = K x BW^0.75 (kcal/day)

Since b = 0.75, the dose-scaling exponent is (1 - 0.75) = 0.25:

**Dose_target (mg/kg) = Dose_reference (mg/kg) x (BW_target / BW_reference)^(-0.25)**

Or equivalently:

**Dose_target (mg/kg) = Dose_reference (mg/kg) x (BW_reference / BW_target)^(0.25)**

### Step-by-Step Calculation

1. Identify the reference species dose (mg/kg), route, and frequency
2. Record the reference species body weight (kg)
3. Record the target species body weight (kg)
4. Calculate the ratio: (BW_reference / BW_target)^0.25
5. Multiply the reference dose (mg/kg) by this ratio
6. The result is the estimated dose (mg/kg) for the target species

### Minimum Energy Cost (MEC) Table

The MEC is calculated as **K x BW^0.75**, where K is the taxon-specific constant. MEC values for selected body weights:

| Body Weight (kg) | MEC (kcal/day) Mammal (K=70) | MEC (kcal/day) Non-passerine Bird (K=78) | MEC (kcal/day) Passerine (K=129) | MEC (kcal/day) Reptile at 37°C (K=10) |
|---|---|---|---|---|
| 0.01 | 2.21 | 2.47 | 4.08 | 0.32 |
| 0.025 | 4.41 | 4.91 | 8.12 | 0.63 |
| 0.05 | 7.42 | 8.27 | 13.67 | 1.06 |
| 0.1 | 12.47 | 13.90 | 22.99 | 1.78 |
| 0.25 | 24.81 | 27.66 | 45.74 | 3.54 |
| 0.5 | 41.74 | 46.53 | 76.94 | 5.96 |
| 1.0 | 70.00 | 78.00 | 129.00 | 10.00 |
| 5.0 | 233.15 | 259.88 | 429.66 | 33.30 |
| 10.0 | 392.08 | 437.01 | 722.49 | 56.01 |
| 25.0 | 780.08 | 869.49 | 1437.54 | 111.44 |
| 50.0 | 1312.07 | 1462.62 | 2418.60 | 187.44 |
| 100.0 | 2213.59 | 2467.53 | 4079.50 | 316.23 |

## Practical Examples

### Example 1: Scaling an Antibiotic from Dog to Raccoon

**Problem**: Enrofloxacin is dosed at 5 mg/kg PO SID in a 15-kg dog. What is the estimated dose for a 6-kg raccoon?

**Calculation**:
- Dose_raccoon = 5 mg/kg x (15 / 6)^0.25
- = 5 x (2.5)^0.25
- = 5 x 1.257
- = **6.3 mg/kg PO SID**

### Example 2: Scaling an Analgesic from Domestic Cat to Sand Cat

**Problem**: Buprenorphine is dosed at 0.02 mg/kg IM in a 4.5-kg domestic cat. What is the estimated dose for a 2.5-kg sand cat (*Felis margarita*)?

**Calculation**:
- Dose_sand cat = 0.02 mg/kg x (4.5 / 2.5)^0.25
- = 0.02 x (1.8)^0.25
- = 0.02 x 1.158
- = **0.023 mg/kg IM**

Note: For closely related species of similar size, the correction factor is small, and the reference dose may be used without adjustment.

### Example 3: Scaling from Mammal to Mammal — Large Size Difference

**Problem**: Meloxicam is dosed at 0.2 mg/kg PO in a 500-kg horse. What is the estimated dose for a 5,000-kg elephant?

**Calculation**:
- Dose_elephant = 0.2 mg/kg x (500 / 5000)^0.25
- = 0.2 x (0.1)^0.25
- = 0.2 x 0.562
- = **0.11 mg/kg PO**

The lower per-kilogram dose for the larger animal reflects its lower mass-specific metabolic rate.

### Example 4: Cross-Taxon Scaling Using MEC

**Problem**: A drug is dosed at 10 mg/kg in a 1-kg domestic pigeon (non-passerine). Estimate the dose for a 1-kg iguana at POTZ (37°C equivalent).

**Calculation using MEC approach**:
- MEC_pigeon (1 kg non-passerine) = 78 x 1^0.75 = 78 kcal/day
- MEC_iguana (1 kg reptile at 37°C) = 10 x 1^0.75 = 10 kcal/day
- Dose_iguana = 10 mg/kg x (10 / 78) = **1.3 mg/kg**

This large reduction reflects the much lower metabolic rate of the ectothermic reptile. **However, cross-taxon scaling carries substantial uncertainty** (see Limitations).

## Dosing Frequency Adjustment

Allometric scaling also predicts that drug half-lives increase with body size. Larger animals eliminate drugs more slowly (per-kilogram basis) and may require less frequent dosing:

**Interval_target = Interval_reference x (BW_target / BW_reference)^0.25**

### Example

If the dosing interval for enrofloxacin in a 15-kg dog is every 24 hours, the estimated interval for a 200-kg lion would be:

- Interval_lion = 24 h x (200 / 15)^0.25
- = 24 x (13.33)^0.25
- = 24 x 1.91
- = **~46 hours (round to q 48 h)**

## Limitations and Cautions

Allometric scaling is a useful starting point but has important limitations that must be understood to avoid clinical errors.

### When Allometric Scaling Works Best

- Scaling between closely related species of different sizes within the same taxon (e.g., small felid to large felid, small parrot to large parrot)
- Drugs eliminated primarily by metabolism (hepatic clearance), which correlates well with metabolic rate
- Drugs with wide therapeutic indices (large safety margins)

### When Allometric Scaling Is Unreliable

| Limitation | Explanation | Clinical Consequence |
|---|---|---|
| Cross-taxon extrapolation | Scaling between mammals, birds, reptiles, and amphibians carries high uncertainty due to fundamentally different physiology | Use taxon-specific reference doses; never scale directly from mammal to reptile without MEC correction |
| Renal clearance | Drugs primarily eliminated by glomerular filtration scale more closely with BW^1.0 than BW^0.75 | Allometric scaling may underestimate doses in small animals for renally cleared drugs |
| Species-specific metabolism | Phase I and Phase II hepatic enzyme activity varies unpredictably across species (e.g., cats lack UGT1A6 glucuronidation, birds have different CYP isoforms) | No formula can predict idiosyncratic species deficiencies |
| Protein binding | Differences in plasma protein binding alter free drug concentration independently of body size | May significantly affect drugs with >95% protein binding |
| Toxic species sensitivities | Some toxicities are species-specific and not predictable by scaling (e.g., ivermectin in chelonians, diclofenac in vultures, acetaminophen in cats) | Always check for known species contraindications before applying scaled doses |
| Ectotherm temperature dependence | Reptile and amphibian metabolism varies with ambient temperature; MEC tables assume a reference temperature | Adjust doses and intervals for the actual body temperature of ectothermic patients |
| Very small or very large body sizes | At extreme body sizes, the 0.75 exponent may not hold precisely | Exercise extra caution at body weights <10 g or >5,000 kg |

### Best Practices

1. **Use allometric scaling as a starting point, not a definitive answer.** Always prefer published species-specific pharmacokinetic data when available.
2. **Start at the low end of the calculated dose range** and titrate upward based on clinical response and monitoring.
3. **Scale within taxa when possible** (mammal to mammal, bird to bird). Cross-taxon scaling should be a last resort.
4. **Use the closest phylogenetic relative** as the reference species rather than defaulting to domestic species.
5. **Account for temperature** in ectotherms. A reptile at 25°C has a metabolic rate roughly half that at 35°C; dose accordingly.
6. **Monitor drug levels** (therapeutic drug monitoring) when available, especially for drugs with narrow therapeutic indices (aminoglycosides, anticonvulsants).
7. **Document and share results.** Every clinical use of allometric scaling in a novel species is an opportunity to contribute to the pharmacokinetic knowledge base. Publish case reports.

## Quick Reference: Scaling Factors

The dose-scaling factor **(BW_ref / BW_target)^0.25** for common body weight ratios:

| BW_ref / BW_target | Scaling Factor | Effect on Dose (mg/kg) |
|---|---|---|
| 0.01 | 0.316 | Target dose is ~32% of reference dose |
| 0.1 | 0.562 | Target dose is ~56% of reference dose |
| 0.5 | 0.841 | Target dose is ~84% of reference dose |
| 1.0 | 1.000 | No adjustment (same body weight) |
| 2.0 | 1.189 | Target dose is ~119% of reference dose |
| 5.0 | 1.495 | Target dose is ~150% of reference dose |
| 10.0 | 1.778 | Target dose is ~178% of reference dose |
| 50.0 | 2.659 | Target dose is ~266% of reference dose |
| 100.0 | 3.162 | Target dose is ~316% of reference dose |

**Interpretation**: When the reference species is larger than the target species (ratio >1), the target species receives a higher mg/kg dose (smaller animals need more drug per kilogram). When the reference species is smaller (ratio <1), the target species receives a lower mg/kg dose.

## Further Reading

- Mahmood I. Application of allometric principles for the prediction of pharmacokinetics in human and veterinary drug development. *Advanced Drug Delivery Reviews*. 2007.
- Hunter RP. Interspecies allometric scaling. *Handbook of Experimental Pharmacology*. 2010.
- Sedgwick CJ. Allometric scaling and emergency care for the exotic zoo and wild animals. *Veterinary Clinics of North America: Exotic Animal Practice*. 1998.
- West GB, Brown JH, Enquist BJ. A general model for the origin of allometric scaling laws in biology. *Science*. 1997;276:122-126.
