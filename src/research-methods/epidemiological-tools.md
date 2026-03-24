# Epidemiological Tools for Wildlife Health

## Introduction

Epidemiology provides the quantitative framework for understanding disease patterns in populations. For wildlife veterinarians, epidemiological tools are essential for moving beyond individual clinical cases to population-level understanding: how common is a disease, what drives its occurrence, how is it spreading, and what interventions are most likely to succeed? This chapter covers the core epidemiological study designs and analytical approaches applicable to wildlife disease investigation.

## Study Designs in Wildlife Epidemiology

### Cross-Sectional Surveys

Cross-sectional surveys are the workhorse of wildlife disease epidemiology, providing snapshots of disease status across populations:

**Design principles:**
- Define the target population clearly (species, geographic area, time frame)
- Use probability-based sampling when possible to obtain representative estimates
- Collect data on both disease status and potential risk factors simultaneously

**Applications in wildlife:**
- Seroprevalence surveys for exposure to specific pathogens
- Estimating parasite prevalence and intensity across host populations
- Assessing body condition, contaminant levels, or health biomarkers across populations
- Baseline health assessments before management interventions

**Analysis:**
- Calculate point prevalence with 95% confidence intervals
- Adjust for imperfect diagnostic test sensitivity and specificity (apparent vs. true prevalence)
- Explore associations between risk factors and disease status using chi-square tests, logistic regression, or multi-variable models

**Limitations:**
- Cannot determine whether exposure preceded disease (temporal ambiguity)
- Subject to survival bias (only living animals are sampled)
- Prevalence reflects both incidence and duration; high prevalence may indicate high incidence or long duration

### Case-Control Studies

Case-control studies are efficient designs for investigating risk factors, particularly for rare diseases:

**Design in wildlife context:**
- **Cases**: Animals with the disease or condition of interest (detected through surveillance, mortality events, or clinical observation)
- **Controls**: Animals without the disease, selected to represent the population from which cases arose
- Compare the frequency of potential exposures or risk factors between cases and controls

**Challenges in wildlife:**
- **Control selection**: Defining the appropriate source population for controls is difficult when population boundaries are unclear
- **Exposure ascertainment**: Retrospective assessment of exposure (habitat use, diet, contacts) relies on indirect data (telemetry, isotope analysis, habitat modeling)
- **Matching**: Matching controls to cases on confounders (age, sex, location) improves validity but requires individual-level data

**Analysis:**
- Calculate odds ratios (OR) for each exposure
- Use conditional logistic regression for matched designs
- Multi-variable models to adjust for confounding

**Wildlife example:** Investigating risk factors for white-nose syndrome severity in bat hibernacula by comparing characteristics of high-mortality and low-mortality sites.

### Cohort Studies

Cohort studies follow groups of individuals over time and are the strongest observational design for establishing risk factors:

**Design in wildlife:**
- Identify a cohort of individuals (e.g., marked or collared animals)
- Classify individuals by exposure status at baseline
- Follow over time to observe who develops the outcome of interest

**Prospective vs. retrospective:**
- **Prospective**: Follow subjects forward from enrollment; gold standard but expensive and time-consuming
- **Retrospective**: Use existing records (e.g., banding databases, long-term monitoring data) to reconstruct cohorts

**Analysis:**
- Calculate incidence rates (new cases per animal-time at risk)
- Estimate risk ratios (RR) or hazard ratios (HR) comparing exposed and unexposed groups
- Survival analysis methods (Kaplan-Meier, Cox regression) to account for variable follow-up

**Wildlife example:** Following a cohort of GPS-collared wolves to compare disease incidence between packs in areas with and without domestic dog contact.

## Outbreak Investigation

### The Outbreak Investigation Framework

When unusual morbidity or mortality is detected in a wildlife population, a systematic investigation follows:

**Step 1: Confirm the outbreak**
- Verify that reported cases are real (confirm diagnoses)
- Determine whether the number of cases exceeds expected baseline levels
- Distinguish true outbreaks from increased surveillance or reporting effort

**Step 2: Define the case**
- Develop a case definition with clinical, temporal, geographic, and species criteria
- Categories: confirmed (laboratory-confirmed), probable (clinical signs plus epidemiological link), suspect (clinical signs only)
- Case definitions may be refined as the investigation progresses

**Step 3: Find and count cases**
- Active case-finding through increased surveillance, field surveys, and partner notifications
- Systematic case enumeration with standardized data collection
- Report to relevant authorities (WOAH, national veterinary services)

**Step 4: Describe the outbreak**
- **Temporal**: Epidemic curve (epi curve) showing cases over time; shape indicates transmission pattern:
  - Point source: sharp peak, narrow curve
  - Continuous common source: plateau pattern
  - Propagated (animal-to-animal): successive waves
- **Spatial**: Map case locations; identify clustering; relate to environmental features
- **Individual characteristics**: Species, age, sex, body condition, habitat type

**Step 5: Generate hypotheses**
- Based on descriptive epidemiology, clinical and pathological findings, and ecological knowledge
- Consider multiple hypotheses (infectious, toxic, nutritional, environmental)

**Step 6: Test hypotheses**
- Analytical epidemiology (case-control or cohort studies nested within the outbreak)
- Laboratory testing (pathogen isolation, toxicology, histopathology)
- Environmental investigation (water/soil/food testing)

**Step 7: Implement control measures**
- May begin before investigation is complete if probable cause is identified
- Carcass removal and disposal to reduce environmental contamination
- Movement restrictions at wildlife-livestock interfaces
- Vaccination if available and indicated
- Habitat management to reduce exposure risk

**Step 8: Communicate findings**
- Situation reports to partner agencies
- Public communication if zoonotic risk exists
- Scientific publication for broader knowledge sharing

## Calculating Disease Measures

### Prevalence

**Point prevalence:**

```
Point prevalence = Number of existing cases at a point in time / Total population at that point in time
```

- Appropriate for cross-sectional surveys
- Adjust for diagnostic test performance:

```
True prevalence = (Apparent prevalence + Specificity - 1) / (Sensitivity + Specificity - 1)
```

**Period prevalence:**

```
Period prevalence = Number of cases during a time period / Average population during the period
```

### Incidence

**Cumulative incidence (risk):**

```
Cumulative incidence = Number of new cases during a period / Population at risk at the start of the period
```

- Requires a defined follow-up period
- Appropriate when all individuals are followed for the same duration

**Incidence rate (person-time / animal-time):**

```
Incidence rate = Number of new cases / Total animal-time at risk
```

- Accounts for variable follow-up (death, emigration, variable enrollment)
- Denominator is typically animal-days, animal-months, or animal-years at risk

### Mortality and Case Fatality

| Measure | Formula | Interpretation |
|---------|---------|----------------|
| Crude mortality rate | Deaths / Population at risk / time | Overall death rate in a population |
| Cause-specific mortality rate | Deaths from specific cause / Population at risk / time | Death rate attributable to a specific disease |
| Case fatality rate | Deaths from disease / Total cases of disease | Proportion of cases that die; reflects disease severity |
| Proportional mortality | Deaths from specific cause / Total deaths | Proportion of all deaths attributable to a cause |

## Risk Factor Analysis

### Univariable Analysis

Initial screening of potential risk factors:

- **Categorical exposures**: Chi-square test or Fisher's exact test (small samples); calculate odds ratios or risk ratios with confidence intervals
- **Continuous exposures**: t-test, Mann-Whitney U test, or logistic regression; assess linearity of association

### Multivariable Analysis

Adjust for confounding and identify independent risk factors:

- **Logistic regression**: Binary outcomes (diseased/not diseased); reports adjusted odds ratios
- **Poisson or negative binomial regression**: Count outcomes (parasite burden); accounts for overdispersion
- **Cox proportional hazards regression**: Time-to-event outcomes (survival, time to infection)
- **Mixed-effects models**: Account for hierarchical data structure (individuals within herds, sites within regions)

### Model Building Strategy

1. Include variables with biological plausibility and p < 0.20 in univariable screening
2. Check for collinearity among predictors (variance inflation factor > 5 suggests problematic collinearity)
3. Use backward elimination, forward selection, or information-theoretic approaches (AIC) for model selection
4. Assess model fit (Hosmer-Lemeshow test, residual plots)
5. Validate with independent data or cross-validation when possible
6. Report effect estimates with confidence intervals and biological interpretation

## Disease Mapping

### Approaches to Spatial Visualization

- **Point maps**: Plot individual case locations; simple but may reveal sensitive location data
- **Choropleth maps**: Shade geographic units (counties, grid cells) by disease frequency; clear for communication but subject to the modifiable areal unit problem (results depend on boundary choice)
- **Kernel density estimation**: Smooth case density across the landscape; visually intuitive
- **Risk surface maps**: Display predicted disease risk across space based on environmental covariates

### Tools for Disease Mapping

- QGIS (free, open-source GIS)
- ArcGIS (commercial; widely used in government and academia)
- R spatial packages: `sf`, `terra`, `tmap`, `leaflet`
- Google Earth Engine for satellite-derived environmental data

## Cluster Detection

### Identifying Non-Random Spatial or Temporal Patterns

Cluster detection methods help determine whether cases are more aggregated than expected:

- **SaTScan (spatial scan statistic)**: Uses moving circular or elliptical windows to identify spatial, temporal, and space-time clusters. Most widely used method in wildlife and public health.
- **Global clustering tests**: Moran's I, Getis-Ord general G -- assess whether there is overall spatial autocorrelation in case distribution
- **Local clustering tests**: Getis-Ord Gi*, local Moran's I -- identify specific locations that are hot spots or cold spots
- **Knox test**: Detects space-time interaction (cases that are close in both space and time more often than expected by chance)

### Interpretation Considerations

- Statistical significance does not equal biological meaningfulness; interpret clusters in ecological context
- Multiple testing can inflate false-positive rates; apply appropriate corrections
- Cluster shape may not match circular scan windows; consider flexible spatial scan statistics
- Underlying population distribution must be accounted for (more cases where more animals live is expected, not evidence of clustering)

## Practical Epidemiological Challenges in Wildlife

### Imperfect Detection

Not all animals in a population are detected during surveys. Failure to account for imperfect detection biases prevalence and incidence estimates downward. Solutions include:

- Occupancy models that explicitly estimate detection probability
- Capture-recapture frameworks that separate detection from biological processes
- Repeat surveys at the same sites to estimate detection probability

### Diagnostic Test Limitations

- Test sensitivity and specificity are often unknown for wildlife species
- Cross-reactivity in serological tests may be higher in wildlife due to exposure to diverse, poorly characterized pathogens
- Validation studies using known positive and negative wildlife samples are essential but rarely available
- Bayesian latent class analysis can estimate test accuracy without a gold standard

### Non-Independent Observations

Wildlife data frequently violate independence assumptions:

- Individuals within social groups share exposures and pathogens
- Spatial proximity creates correlated health outcomes
- Repeated sampling of the same individuals introduces temporal autocorrelation
- Solutions: mixed-effects models, generalized estimating equations (GEE), spatial regression models

### Population Denominators

Calculating rates and prevalences requires knowing the population at risk, which is often unknown for wildlife:

- Use mark-recapture or distance sampling estimates for population size
- Report proportions with clearly defined denominators (e.g., prevalence among sampled animals rather than estimated population prevalence)
- Use relative risk measures that do not require population size (odds ratios from case-control studies)

## Summary

Epidemiological tools provide the quantitative rigor needed to understand wildlife disease at the population level. From cross-sectional surveys to outbreak investigations, from risk factor analysis to disease mapping, these methods allow wildlife veterinarians to move from clinical observation to evidence-based management. Mastering these tools, while remaining aware of their limitations in the wildlife context, is essential for any wildlife veterinarian engaged in disease surveillance, research, or management.
