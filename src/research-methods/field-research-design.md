# Field Research Design

## Introduction

Field research is the backbone of wildlife veterinary science. Unlike controlled laboratory environments, wildlife field research takes place in complex, dynamic ecosystems where study subjects are free-ranging, environmental variables are uncontrolled, and logistical challenges abound. Thoughtful study design is therefore critical to producing valid, interpretable results that advance wildlife health and conservation.

## Study Design Types

### Observational Studies

Most wildlife research is observational because manipulating wild populations is often impractical, unethical, or both.

#### Cross-Sectional Studies
- **Design**: A snapshot of a population at a single point in time
- **Applications**: Estimating disease prevalence, characterizing health parameters, identifying correlations between exposure and outcome
- **Strengths**: Relatively quick and inexpensive; can generate hypotheses
- **Limitations**: Cannot establish temporal relationships or causation; susceptible to prevalence-incidence bias (only captures individuals that survive long enough to be sampled)
- **Wildlife example**: Serological survey of a deer population for chronic wasting disease prion exposure during a single hunting season

#### Case-Control Studies
- **Design**: Compare individuals with a condition (cases) to individuals without (controls) and look backward for differences in exposure
- **Applications**: Investigating risk factors for rare diseases or mortality events
- **Strengths**: Efficient for rare outcomes; relatively quick
- **Limitations**: Prone to selection bias and recall/ascertainment bias; difficult to define appropriate controls in wildlife
- **Wildlife example**: Comparing habitat characteristics around nesting sites of condors with and without lead poisoning

#### Cohort Studies
- **Design**: Follow a group of individuals over time to observe who develops a condition
- **Applications**: Estimating incidence, identifying risk factors, understanding disease progression
- **Strengths**: Can establish temporal relationships; estimates incidence directly
- **Limitations**: Expensive and time-consuming; loss to follow-up (death, emigration) is a major challenge in wildlife
- **Wildlife example**: Monitoring a cohort of radio-collared elk for five years to assess bovine tuberculosis incidence and survival

### Experimental Studies

True experiments involve manipulation of variables and random assignment to treatment groups.

#### Randomized Controlled Trials
- **Design**: Randomly assign subjects to treatment and control groups; compare outcomes
- **Applications**: Testing vaccine efficacy, evaluating treatment protocols, assessing management interventions
- **Strengths**: Strongest evidence for causation
- **Limitations**: Often infeasible or unethical in wildlife; logistically demanding; may not reflect real-world conditions
- **Wildlife example**: Randomized trial of oral rabies vaccine baits in raccoon populations, with vaccinated and control areas

#### Before-After-Control-Impact (BACI)
- **Design**: Measure outcomes at impact and control sites before and after an intervention or event
- **Applications**: Assessing effects of management actions, habitat changes, or pollution events on wildlife health
- **Strengths**: Controls for both temporal trends and spatial variation
- **Limitations**: Requires pre-event baseline data; finding appropriate control sites can be challenging
- **Wildlife example**: Assessing the health impact of an oil spill on seabird populations by comparing pre- and post-spill data at affected and unaffected colonies

### Quasi-Experimental Studies

When randomization is not possible but some experimental control exists:

- **Natural experiments**: Exploit naturally occurring variation (e.g., comparing disease dynamics in populations on either side of a natural geographic barrier)
- **Regression discontinuity**: Exploit sharp thresholds (e.g., comparing wildlife health in areas just above and below a pollution threshold)
- **Interrupted time series**: Analyze trend data before and after an intervention without a control group

## Sampling Strategies

### Random Sampling

- **Simple random sampling**: Every individual or unit has an equal probability of selection. Ideal in theory but rarely achievable in wildlife studies where access to all individuals is impossible.
- **Implementation**: Use random point generators within a study area; sample all animals encountered at random locations; use lottery systems for selecting from a list of known individuals.

### Stratified Sampling

- **Design**: Divide the population into subgroups (strata) based on relevant characteristics (habitat type, age class, sex, geographic region) and sample within each stratum
- **Advantages**: Ensures representation of important subgroups; improves precision of estimates when strata differ meaningfully
- **Applications**: Sampling across habitat types to assess how land use affects disease prevalence; stratifying by age class when disease susceptibility varies with age
- **Considerations**: Requires prior knowledge of population structure; allocation of effort across strata should be proportional to variability or to research priorities

### Convenience Sampling

- **Design**: Sample whatever individuals are available (e.g., road-killed animals, hunter-harvested specimens, rehabilitation admissions)
- **Advantages**: Low cost; often the only feasible approach for rare species or opportunistic situations
- **Limitations**: Non-random; results may not be representative of the wider population. Hunter-harvested samples may overrepresent certain age classes, sexes, or health states.
- **Mitigation**: Document the sampling frame clearly; discuss potential biases in interpretation; compare sample demographics to known population structure where possible

### Opportunistic Sampling

- **Design**: Collecting data whenever the opportunity arises, without a predetermined sampling plan
- **Advantages**: Can yield valuable data from rare events (mass mortality, unusual species encounters)
- **Limitations**: Cannot be used for most quantitative analyses without explicit bias adjustment
- **Best use**: Hypothesis generation, case reports, and building reference collections

## Field Survey Methods

### Mark-Recapture

Mark-recapture methods estimate population size and demographic parameters essential for disease modeling:

- **Closed population models** (Lincoln-Petersen, Chapman): Assume no births, deaths, immigration, or emigration between capture occasions. Suitable for short study periods.
- **Open population models** (Jolly-Seber, POPAN): Allow for births, deaths, and movement. Suitable for longer-term studies.
- **Robust design**: Combines closed (within primary periods) and open (between primary periods) models for comprehensive demographic estimation.
- **Multi-state models**: Allow individuals to transition between states (e.g., infected/uninfected, present/absent), directly linking health status to demographic parameters.

**Marking methods in wildlife:**

| Method | Taxa | Considerations |
|--------|------|----------------|
| Ear tags, flipper tags | Mammals, sea turtles | Tag loss, tissue reaction |
| Leg bands | Birds | Band injury, readability at distance |
| PIT tags (microchips) | Multiple taxa | Requires recapture for reading |
| Natural markings (photo-ID) | Cetaceans, felids, amphibians | Non-invasive; requires image quality |
| GPS/satellite collars | Large mammals, birds | Weight limits, battery life, collar effects |
| Genetic mark-recapture | Multiple taxa | Non-invasive; uses genotypes as individual identifiers |
| Tattoos, toe clips | Small mammals, amphibians | Welfare concerns; increasingly replaced by alternatives |

### Distance Sampling

Distance sampling estimates population density and abundance from survey transects:

- **Line transects**: Observer walks a predetermined line and records perpendicular distance to each detected animal. Detection probability is modeled as a function of distance.
- **Point transects**: Observer stands at fixed points and records distances to detected animals.
- **Assumptions**: Animals on the transect line/point are detected with certainty; animals are detected at their initial position; distances are measured accurately.
- **Health applications**: Estimating population density for disease prevalence calculations; comparing densities in areas with different management or habitat conditions.

### Camera Trap Surveys

Camera traps provide non-invasive population and behavioral data:

- **Occupancy estimation**: Determine presence/absence of species at survey sites; model detection probability
- **Density estimation**: Spatially explicit capture-recapture (SECR) models using individually identifiable species
- **Activity patterns**: Temporal activity data can reveal behavioral changes associated with disease or environmental stressors
- **Body condition scoring**: Systematic evaluation of body condition from images
- **Health assessment**: Detection of clinical signs visible in photographs (mange, tumors, injuries)

**Design considerations:**
- Camera spacing relative to species home range
- Survey duration and number of trap-nights needed
- Camera placement (height, angle, bait/lure use)
- Data management for large image volumes (automated species classification using machine learning)

## Power Analysis for Wildlife Studies

### Why Power Analysis Matters

Statistical power is the probability of detecting an effect if one truly exists. Low-powered studies waste resources and risk missing biologically important findings.

### Components of Power Analysis

- **Effect size**: The magnitude of the difference or relationship you want to detect. Must be biologically meaningful, not just statistically significant.
- **Sample size**: The number of independent observations (individuals, sites, occasions).
- **Significance level (alpha)**: Typically 0.05, but may be adjusted for multiple comparisons or conservation-critical decisions.
- **Power (1-beta)**: Conventionally 0.80, meaning an 80% chance of detecting a true effect.

### Conducting Power Analysis

- **A priori power analysis**: Before the study, determine the sample size needed to detect a specified effect size with desired power. Essential for study planning and funding applications.
- **Post hoc power analysis**: After the study, calculate the power achieved. Controversial and often uninformative; better to report effect sizes and confidence intervals.
- **Simulation-based power analysis**: For complex designs (multi-level, spatial, occupancy), simulating data under expected scenarios is often the most reliable approach.

### Tools for Power Analysis

- **G*Power**: Free software for standard designs (t-tests, ANOVA, regression, chi-square)
- **R packages**: `pwr` for basic designs; `simr` for mixed-effects models; custom simulation scripts for complex designs
- **Wildlife-specific considerations**: Account for capture probability, detection probability, clustering, and expected dropout/mortality rates

### Practical Advice for Low-Power Situations

When small sample sizes are unavoidable:

- Focus on effect sizes rather than p-values
- Use Bayesian approaches that quantify evidence without relying on arbitrary significance thresholds
- Consider meta-analysis or data pooling across studies and populations
- Use information-theoretic approaches (AIC model selection) to evaluate competing hypotheses
- Report confidence intervals and interpret them in the context of biological significance
- Use exact tests rather than asymptotic tests for small samples
- Consider adaptive study designs that allow sample size re-evaluation

## Practical Considerations for Field Study Design

### Pilot Studies

Before committing resources to a full study:

- Conduct a pilot to estimate detection probability, capture success, and logistical feasibility
- Assess variability in key outcome measures to inform power analysis
- Test field protocols and data collection instruments
- Train field personnel and evaluate inter-observer reliability

### Temporal Design

- **Seasonal timing**: Disease prevalence, body condition, and behavior vary seasonally; timing must match the research question
- **Study duration**: Chronic diseases and population-level effects require multi-year studies
- **Sampling frequency**: Balance data needs with capture stress and logistical capacity
- **Repeated measures**: Same individuals sampled over time provide more information but require reliable individual identification

### Spatial Design

- **Study area delineation**: Define study area boundaries based on biological relevance, not administrative convenience
- **Spatial replication**: Include multiple sites to increase generalizability
- **Spatial autocorrelation**: Nearby sites may not be independent; account for spatial structure in analysis
- **Landscape context**: Record landscape features that may influence health outcomes (habitat type, proximity to agriculture, elevation, water sources)

### Field Data Recording

- Use standardized data sheets (paper or electronic) with pre-defined fields and coding systems
- Record GPS coordinates for every observation, capture, or sample collection
- Photograph specimens, lesions, and habitats systematically
- Maintain chain of custody documentation for all biological samples
- Back up data daily; use cloud-synced systems where connectivity allows

## Summary

Rigorous field research design is the foundation on which all subsequent analysis and interpretation rest. By carefully selecting study designs appropriate to the question, applying sampling strategies that minimize bias, using validated field survey methods, and conducting thorough power analysis, wildlife veterinarians can produce research that withstands scientific scrutiny and meaningfully advances wildlife health and conservation.
