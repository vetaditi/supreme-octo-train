# Population Health Assessment

## Designing Health Surveys

Population health assessment is the systematic evaluation of health parameters across a wildlife population to characterize baseline conditions, detect disease, and monitor trends over time. Unlike clinical veterinary medicine, the unit of concern is the population rather than the individual.

### Survey Design Principles

Effective health surveys require careful planning before any animal is captured or sampled:

- **Define clear objectives**: Is the goal to establish baseline health parameters, detect a specific pathogen, monitor trends over time, or assess the impact of an environmental stressor?
- **Determine the target population**: Define the geographic and demographic boundaries of the population to be sampled.
- **Select a sampling strategy**: Random sampling is ideal but rarely achievable in wildlife. Stratified sampling (by age, sex, location, season) is more practical and often more informative.
- **Calculate sample size**: Power analysis should guide sample size determination. For prevalence estimation, sample size depends on expected prevalence, desired precision, and confidence level. For rare diseases, larger sample sizes are needed.
- **Plan for logistics**: Capture method, personnel requirements, sample processing capacity, and transport logistics all constrain survey design.

### Sample Size Estimation for Prevalence Studies

| Expected Prevalence | 95% CI Width +/- 5% | 95% CI Width +/- 10% |
|---|---|---|
| 5% | 73 | 18 |
| 10% | 138 | 35 |
| 25% | 288 | 72 |
| 50% | 384 | 96 |

These values assume simple random sampling from a large population. For small populations, finite population correction should be applied.

### Sampling Bias Considerations

Wildlife health surveys are inherently subject to biases that must be acknowledged and, where possible, mitigated:

- **Capture bias**: Animals that are easier to capture may differ systematically from those that are not (e.g., sick animals may be more approachable or less approachable depending on species)
- **Seasonal bias**: Health parameters vary seasonally; surveys conducted in a single season may not represent annual health status
- **Age and sex bias**: Capture methods often preferentially capture certain demographic groups
- **Survivor bias**: Sampling live animals misses individuals that have already died from disease

## Establishing Baseline Health Parameters

### Reference Range Development for Wild Populations

Reference ranges (often called "normal values") for wild species cannot simply be borrowed from domestic animal medicine. Development of species-specific reference ranges requires:

1. **Sample a representative group of clinically healthy animals**: Minimum of 40 individuals is recommended by the American Society for Veterinary Clinical Pathology (ASVCP) for non-parametric reference intervals; 120 individuals for parametric methods.
2. **Standardize pre-analytical conditions**: Capture method, restraint duration, anesthetic protocol, sample handling, and laboratory methods all affect results.
3. **Partition by relevant variables**: Age class, sex, reproductive status, season, and geographic location may warrant separate reference intervals.
4. **Apply appropriate statistical methods**: Non-parametric methods are preferred when sample sizes are small. Robust methods can handle moderate outlier contamination.
5. **Report with confidence intervals**: Reference intervals should be reported with 90% confidence intervals around the upper and lower limits.

### Key Considerations

- **Capture stress effects**: The act of capture itself alters many health parameters. Stress leukograms, hyperglycemia, elevated creatine kinase, and lactic acidosis are common capture artifacts. Documenting chase/handling time is essential.
- **Anesthetic effects**: Different immobilization drugs have different effects on hematology and biochemistry. Protocols should be standardized within a study.
- **Analyzer differences**: Point-of-care analyzers used in field settings may give different results than reference laboratory instruments. Cross-validation is important.

## Health Indices

### Body Condition Assessment

Body condition scoring provides a standardized method to assess nutritional status. Systems vary by taxon:

**Mammals**:
- Visual and palpation-based scoring systems (typically 1-5 or 1-9 scales)
- Key landmarks: ribs, spine, hip bones, tail base fat deposits
- Body condition indices calculated from morphometric measurements (e.g., kidney fat index, marrow fat percentage in ungulates)
- Bioelectrical impedance analysis (BIA) for body composition

**Birds**:
- Pectoral muscle scoring (0-3 scale based on keel bone prominence)
- Furcular fat scoring
- Body mass relative to structural size (e.g., body mass/wing chord ratio)

**Reptiles**:
- Body condition index = log(mass) / log(snout-vent length)
- Tail base width relative to body size (species-specific)
- Visual assessment of fat pad development

**Amphibians**:
- Scaled mass index (SMI)
- Body mass/snout-vent length residuals

### Composite Health Indices

Several approaches combine multiple health parameters into a single score:

- **Health score cards**: Assign points for each parameter within or outside reference range
- **Principal component analysis (PCA)**: Reduce multidimensional health data to composite scores
- **Clinicopathologic index**: Weighted combination of hematology and biochemistry values based on physiological importance

## Stress Physiology

### Glucocorticoid Assessment

Cortisol (or corticosterone in birds, reptiles, and amphibians) is the most widely used biomarker of physiological stress in wildlife:

- **Plasma/serum cortisol**: Reflects acute stress state but is heavily confounded by capture and handling stress. Samples must be collected within 3 minutes of initial disturbance for baseline values.
- **Fecal glucocorticoid metabolites (FGMs)**: Reflect integrated stress over hours to days depending on species gut transit time. Non-invasive collection is a major advantage. Requires species-specific assay validation.
- **Hair/feather cortisol**: Reflects chronic stress over weeks to months corresponding to the growth period. Increasingly used in wildlife studies.
- **Salivary cortisol**: Feasible in some species; less invasive than blood sampling.

### Leukocyte Ratios

The heterophil-to-lymphocyte ratio (H:L) or neutrophil-to-lymphocyte ratio (N:L) serves as an integrated measure of chronic stress:

- Elevated ratios indicate sustained glucocorticoid exposure
- Less susceptible to acute capture stress artifacts than plasma cortisol
- Inexpensive and feasible with basic laboratory equipment
- Must be interpreted with caution as infectious disease, inflammation, and other factors also alter leukocyte ratios

### Other Stress Biomarkers

- **Heat shock proteins (HSP70, HSP90)**: Indicators of cellular stress
- **Oxidative stress markers**: Reactive oxygen metabolites (ROMs), antioxidant capacity
- **Acute phase proteins**: Haptoglobin, serum amyloid A, C-reactive protein (species-dependent availability)
- **Telomere length**: Marker of cumulative life stress and biological aging

## Hematology Interpretation in Wild Species

### Complete Blood Count

Key differences from domestic animal interpretation:

- **Nucleated red blood cells**: Normal in birds, reptiles, amphibians, and fish. Automated cell counters designed for mammals cannot be used without modification.
- **Heterophils vs. neutrophils**: Birds, reptiles, and some mammals have heterophils rather than neutrophils. Functional equivalents but morphologically distinct.
- **Thrombocyte identification**: Birds and reptiles have nucleated thrombocytes that may be confused with small lymphocytes on blood smears.
- **Seasonal variation**: Many species show significant seasonal changes in hematologic parameters related to hibernation, migration, breeding, or environmental cycles.

### Hematology Reference Values: General Patterns

| Parameter | Common Findings in Wildlife |
|---|---|
| PCV/Hematocrit | Highly variable; altitude-adapted species tend higher |
| Total WBC | Often higher in wild vs. captive individuals |
| Heterophil/Neutrophil | Stress leukogram common in captured animals |
| Lymphocytes | May decrease with chronic stress |
| Eosinophils | Often elevated with parasitism; seasonal variation |
| Basophils | Poorly understood in most wildlife species |
| Monocytes | May indicate chronic inflammation or tissue damage |

### Blood Smear Evaluation

Manual blood smear evaluation remains essential in wildlife hematology:

- Estimated WBC count from smear (cells per 10 high-power fields x 2000 = approximate WBC/uL)
- Differential count: Classify 100-200 leukocytes
- RBC morphology: Polychromasia, anisocytosis, hemoparasites
- Hemoparasite screening: *Plasmodium*, *Haemoproteus*, *Leucocytozoon*, *Hepatozoon*, *Trypanosoma*, microfilariae
- Thrombocyte estimate and morphology

## Serum Biochemistry Interpretation

### Core Biochemistry Panel

The following analytes form the core panel for most wildlife health assessments:

**Hepatic indicators**:
- Aspartate aminotransferase (AST): Present in liver, muscle, and other tissues; not liver-specific but sensitive
- Alanine aminotransferase (ALT): More liver-specific in mammals; poor indicator in birds and reptiles
- Bile acids: Useful test of hepatic function; pre- and post-prandial values ideal
- Gamma-glutamyl transferase (GGT): Biliary disease indicator

**Renal indicators**:
- Blood urea nitrogen (BUN) or urea: Affected by protein intake, hydration, and renal function
- Creatinine: Less reliable in wildlife due to variation in muscle mass
- Uric acid: Primary indicator of renal function in birds and reptiles

**Muscle indicators**:
- Creatine kinase (CK): Markedly elevated with capture myopathy; peaks 6-12 hours post-capture
- Lactate dehydrogenase (LDH): Less specific than CK; elevated with tissue damage of many types
- Lactate: Indicator of anaerobic metabolism during capture; prognostic for capture myopathy

**Metabolic indicators**:
- Glucose: Stress hyperglycemia is nearly universal in captured wildlife
- Total protein and albumin: Nutritional status and hydration
- Calcium and phosphorus: Metabolic bone disease, reproductive status (hypercalcemia in egg-laying females)
- Electrolytes (Na, K, Cl): Hydration status, renal function

### Interpretation Pitfalls

- **Never interpret wildlife biochemistry using domestic animal reference ranges** without careful consideration of species-specific physiology
- **Lipemia** is common in migratory birds and marine mammals; it interferes with many colorimetric assays
- **Hemolysis** from difficult venipuncture artificially elevates potassium, AST, LDH, and other intracellular analytes
- **Temperature effects**: Reptile and amphibian biochemistry varies with ambient temperature
- **Reproductive effects**: Vitellogenesis in egg-laying species dramatically alters calcium, total protein, triglycerides, and other values

## Practical Field Protocols

### Minimum Data Set for Wildlife Health Assessment

Every captured animal should have the following recorded, regardless of the study's specific objectives:

1. **Identification**: Species, individual ID (tag, band, microchip), capture location (GPS), date and time
2. **Capture data**: Method, chase/pursuit duration, handling duration, drugs administered
3. **Signalment**: Age class, sex, reproductive status
4. **Morphometrics**: Body mass, standard body measurements (species-specific)
5. **Body condition score**: Using species-appropriate scoring system
6. **Physical examination findings**: Abnormalities, injuries, ectoparasites, lesions
7. **Samples collected**: Type, number, storage method, disposition
8. **Outcome**: Released, held for treatment, died, euthanized

### Point-of-Care Diagnostics

Field-deployable analyzers have expanded the range of diagnostics available during wildlife captures:

- **Portable blood analyzers** (iSTAT, Vetscan): Provide rapid hematology and biochemistry results
- **Glucometers**: Useful but must be validated for each species (many are calibrated for human blood)
- **Lactate meters**: Valuable for monitoring capture myopathy risk
- **Refractometer**: Total solids estimation, urine specific gravity
- **Rapid antigen/antibody tests**: Available for some wildlife pathogens
- **Portable ultrasound**: Body fat assessment, pregnancy diagnosis, cardiac evaluation

## Data Management and Long-term Monitoring

### Database Design

Population health data are only useful if they can be retrieved, analyzed, and compared over time:

- Use standardized data entry forms to minimize transcription errors
- Employ relational database structures linking capture events, individual animals, samples, and results
- Follow established data standards (e.g., Darwin Core for biodiversity data)
- Plan for data archiving and sharing from the outset

### Longitudinal Health Monitoring

Long-term monitoring programs require:

- **Consistent protocols**: Methodological changes over time confound trend analysis
- **Adequate sample sizes sustained over time**: Sporadic sampling reduces statistical power
- **Integration with demographic monitoring**: Health data gain power when linked to survival, reproduction, and population trend data
- **Trigger thresholds**: Pre-defined parameter values that initiate investigation or management response
- **Regular reporting**: Annual health summaries for management agencies and stakeholders
