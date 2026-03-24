# Biostatistics for Wildlife Research

## Introduction

Biostatistics is the application of statistical methods to biological data. For wildlife veterinarians, statistical literacy is not merely an academic requirement but a practical necessity: the ability to design studies, analyze data, and critically evaluate published research depends on a solid understanding of statistical principles. This chapter covers the statistical methods most relevant to wildlife health research, from foundational concepts to advanced modeling approaches.

## Descriptive Statistics for Wildlife Data

### Summarizing Continuous Data

Before any formal analysis, data must be explored and summarized:

- **Central tendency**: Mean, median, and mode. The median is often preferred for wildlife data, which frequently exhibit skewed distributions (e.g., parasite counts, contaminant concentrations).
- **Variability**: Standard deviation, interquartile range (IQR), range, and coefficient of variation (CV). The CV is particularly useful for comparing variability across species or parameters with different scales.
- **Distribution shape**: Skewness and kurtosis quantify departures from normality. Histograms, Q-Q plots, and density plots provide visual assessment.

### Summarizing Categorical Data

- Frequencies and proportions for disease status, sex, age class, habitat type
- Contingency tables for cross-tabulations of categorical variables
- Bar charts and mosaic plots for visualization

### Wildlife-Specific Considerations

- **Aggregation indices** for parasite data: Variance-to-mean ratio, negative binomial k parameter to characterize overdispersed distributions typical of macroparasite counts
- **Body condition indices**: Scaled mass index, residual body mass indices derived from body mass-structural size regressions
- **Reference intervals**: Establishing species-specific reference ranges for hematology and clinical chemistry requires appropriate statistical methods (e.g., nonparametric reference intervals per ASVCP/CLSI guidelines)

## Hypothesis Testing

### Fundamentals

- **Null hypothesis (H0)**: No effect, no difference, no association
- **Alternative hypothesis (H1)**: An effect, difference, or association exists
- **P-value**: The probability of observing data as extreme as or more extreme than observed, given that H0 is true
- **Significance level (alpha)**: The threshold below which p-values are considered statistically significant (conventionally 0.05, but context-dependent)
- **Type I error**: Rejecting H0 when it is true (false positive)
- **Type II error**: Failing to reject H0 when it is false (false negative)

### Common Tests

| Data Type | Comparison | Parametric Test | Non-Parametric Alternative |
|-----------|-----------|----------------|--------------------------|
| Continuous | Two groups | Independent t-test | Mann-Whitney U test |
| Continuous | Two paired groups | Paired t-test | Wilcoxon signed-rank test |
| Continuous | >2 groups | One-way ANOVA | Kruskal-Wallis test |
| Categorical | Two groups | Chi-square test | Fisher's exact test |
| Continuous | Association | Pearson correlation | Spearman rank correlation |

### Beyond P-Values

Modern statistical practice emphasizes:

- **Effect sizes**: Quantify the magnitude of differences or associations (Cohen's d, odds ratios, correlation coefficients). A statistically significant result with a trivial effect size may not be biologically meaningful.
- **Confidence intervals**: Report 95% CIs for all estimates. A CI that includes the null value conveys similar information to a non-significant p-value but provides additional insight into the range of plausible effects.
- **Practical significance**: Consider whether detected effects are large enough to matter biologically or for management decisions.

## Generalized Linear Models (GLMs)

### When Linear Regression Is Not Enough

Standard linear regression assumes normally distributed errors and a linear relationship between predictors and outcome. Wildlife data frequently violate these assumptions:

- **Binary outcomes** (infected/not infected): Use logistic regression (binomial family, logit link)
- **Count data** (parasite burden, colony size): Use Poisson regression (Poisson family, log link)
- **Overdispersed counts**: Use negative binomial regression or quasi-Poisson
- **Proportions with known denominators**: Use binomial GLM with logit link
- **Continuous, positive, skewed data** (contaminant concentrations): Use Gamma regression (Gamma family, log link)

### Model Specification

A GLM consists of three components:

1. **Random component**: Specifies the probability distribution of the response variable
2. **Systematic component**: Linear combination of predictor variables (fixed effects)
3. **Link function**: Connects the mean of the response to the linear predictor

### Interpreting GLM Output

- **Logistic regression**: Coefficients are log-odds; exponentiate to obtain odds ratios. An OR > 1 indicates increased odds of the outcome with increasing values of the predictor.
- **Poisson/negative binomial regression**: Coefficients are log-rate ratios; exponentiate to obtain incidence rate ratios.
- **Model fit**: Assess using deviance, AIC, residual plots, and goodness-of-fit tests (e.g., Pearson chi-square for Poisson models)

## Mixed-Effects Models

### Why Mixed-Effects Models Matter for Wildlife Data

Wildlife data are almost always hierarchically structured:

- Repeated measures on the same individual over time
- Multiple individuals within social groups, herds, or colonies
- Multiple sites within regions
- Multiple species within communities

Failing to account for this structure leads to pseudo-replication and inflated Type I error rates.

### Model Structure

- **Fixed effects**: Variables of primary interest (disease status, treatment, environmental covariates)
- **Random effects**: Variables representing the hierarchical structure (individual ID, site, year)
  - **Random intercepts**: Allow the baseline level of the response to vary across groups
  - **Random slopes**: Allow the effect of a predictor to vary across groups

### Implementation in R

```r
# Generalized linear mixed model (binomial response)
library(lme4)
model <- glmer(infection ~ habitat_type + body_condition + (1 | site),
               data = wildlife_data,
               family = binomial)
summary(model)

# Negative binomial mixed model for parasite counts
library(lme4)
library(MASS)
model_nb <- glmer.nb(parasite_count ~ season + age_class + (1 | individual),
                     data = parasite_data)
```

### Key R Packages

| Package | Purpose |
|---------|---------|
| `lme4` | Linear and generalized linear mixed models |
| `nlme` | Linear mixed models with flexible correlation structures |
| `glmmTMB` | GLMMs with extended distributions (zero-inflation, beta) |
| `brms` | Bayesian mixed models via Stan |
| `MCMCglmm` | Bayesian GLMMs with multi-response capabilities |

## Survival Analysis

### Kaplan-Meier Estimation

The Kaplan-Meier estimator provides non-parametric estimates of survival functions:

- Handles right-censored data (individuals lost to follow-up or still alive at study end)
- Produces survival curves showing the proportion surviving over time
- Log-rank test compares survival between groups
- Particularly useful for comparing survival of wildlife across habitat types, exposure categories, or management treatments

### Cox Proportional Hazards Regression

The Cox model assesses the effect of covariates on survival without specifying the baseline hazard function:

```r
library(survival)
cox_model <- coxph(Surv(time, status) ~ sex + body_condition + habitat,
                   data = survival_data)
summary(cox_model)
```

- **Hazard ratio (HR)**: HR > 1 indicates increased risk of the event (death, infection); HR < 1 indicates decreased risk
- **Proportional hazards assumption**: The effect of each covariate on the hazard is constant over time; test using Schoenfeld residuals
- **Extensions**: Time-varying covariates, frailty models (random effects for survival data), competing risks

### Known-Fate Models

For radio-tagged wildlife, known-fate models provide interval-specific survival estimates:

- Animals are checked at regular intervals; status (alive/dead) is determined
- Survival is estimated for each interval and multiplied across intervals for cumulative survival
- Staggered entry and censoring are accommodated
- Implemented in Program MARK and the R package `RMark`

## Occupancy Modeling

### Concept

Occupancy models estimate the probability that a species occupies a site while explicitly accounting for imperfect detection:

- **Psi (psi)**: Probability that a site is occupied
- **p**: Probability of detecting the species at an occupied site during a single survey
- Requires repeated surveys at sites to separate occupancy from detection

### Applications in Wildlife Health

- Estimating the proportion of sites where a pathogen or disease is present
- Modeling factors that influence pathogen occurrence while accounting for imperfect diagnostic or surveillance sensitivity
- Assessing the distribution of disease vectors or reservoir hosts

### Implementation

```r
library(unmarked)
# Create unmarked frame
umf <- unmarkedFrameOccu(y = detection_matrix,
                         siteCovs = site_data,
                         obsCovs = observation_data)

# Fit occupancy model
occ_model <- occu(~ observation_covariates ~ site_covariates, data = umf)
summary(occ_model)
```

### Extensions

- **Multi-season (dynamic) occupancy**: Estimates colonization and extinction rates between seasons
- **Multi-species occupancy**: Joint models for interacting species (e.g., predator-prey, host-pathogen)
- **False-positive occupancy**: Accounts for misidentification in addition to non-detection

## Bayesian Approaches

### Why Bayesian Methods for Wildlife Research?

Bayesian statistics offer several advantages for wildlife data:

- **Small sample sizes**: Bayesian methods can incorporate prior information to improve estimates when data are sparse
- **Complex models**: Hierarchical Bayesian models naturally handle the nested, multi-level structures common in wildlife data
- **Intuitive inference**: Posterior distributions provide direct probability statements about parameters (e.g., "there is a 95% probability that the prevalence is between 10% and 25%")
- **Missing data**: Bayesian frameworks handle missing data more naturally than frequentist approaches
- **Model comparison**: Bayesian model comparison tools (WAIC, LOO-CV) are well-suited for comparing complex models

### Practical Implementation

- **JAGS/BUGS**: Flexible Bayesian modeling languages; interface with R through `rjags`, `R2jags`, `jagsUI`
- **Stan**: Modern probabilistic programming language; interfaces through `rstan` and `brms`
- **NIMBLE**: R-based system for Bayesian and likelihood-based inference; efficient for complex ecological models
- **Prior specification**: Use informative priors when legitimate prior knowledge exists; use weakly informative priors to regularize estimates; conduct sensitivity analyses to assess prior influence

### Applications

- Integrated population models combining survival, reproduction, and count data
- Disease transmission models with uncertain parameters
- Estimating prevalence with imperfect diagnostic tests using Bayesian latent class models
- Joint species distribution models for community-level health assessments

## Dealing with Small Sample Sizes

### Statistical Approaches

- **Exact tests**: Fisher's exact test, exact logistic regression -- do not rely on asymptotic approximations
- **Permutation tests**: Generate the null distribution by resampling the observed data; no distributional assumptions
- **Bayesian methods**: Particularly valuable when informative priors from related species or populations are available
- **Effect size estimation**: Report effect sizes with confidence intervals even when significance is not achieved
- **Pooling and meta-analysis**: Combine data across studies, populations, or species to increase sample size (with appropriate statistical methods for heterogeneity)

### Reporting Standards

When sample sizes are small, transparent reporting is critical:

- State the sample size and how it was determined (or why it could not be larger)
- Report exact p-values rather than significance thresholds
- Provide effect sizes and confidence intervals
- Discuss the limitations imposed by sample size on the conclusions
- Frame findings as preliminary and hypothesis-generating when appropriate

## Information-Theoretic Approaches

### AIC-Based Model Selection

An alternative to null hypothesis significance testing for comparing competing models:

- **Akaike Information Criterion (AIC)**: Balances model fit against complexity; lower AIC indicates a better model
- **Delta AIC**: Difference in AIC between each model and the best model; models within 2 AIC units have substantial support
- **AIC weights**: Relative likelihood of each model; can be interpreted as the probability that a given model is the best model in the candidate set
- **Model averaging**: When no single model is clearly best, average predictions across models weighted by AIC weights

### Implementation

- Define a candidate set of models based on biological hypotheses (not data dredging)
- Fit all models to the same dataset
- Rank by AIC (or AICc for small samples)
- Report model selection table with AIC, delta AIC, AIC weights, and number of parameters

## Software Tools

### R Packages for Wildlife Biostatistics

| Package | Purpose |
|---------|---------|
| `lme4` | Mixed-effects models |
| `survival` | Survival analysis (Kaplan-Meier, Cox) |
| `unmarked` | Occupancy and N-mixture models |
| `MuMIn` | Multi-model inference and model averaging |
| `pwr` | Power analysis |
| `boot` | Bootstrap resampling |
| `MASS` | Negative binomial regression, robust methods |
| `DHARMa` | Residual diagnostics for hierarchical models |
| `ggplot2` | Publication-quality graphics |
| `brms` | Bayesian regression models via Stan |
| `jagsUI` | Interface to JAGS for Bayesian models |
| `RMark` | Interface to Program MARK for capture-recapture and survival |
| `Distance` | Distance sampling analysis |

### Other Software

- **Program MARK**: Gold standard for capture-recapture and known-fate survival analysis
- **DISTANCE**: Purpose-built for distance sampling estimation
- **WinBUGS/OpenBUGS**: Bayesian modeling (largely superseded by JAGS and Stan)
- **SAS, Stata, SPSS**: General statistical packages; less commonly used in wildlife research than R

## Summary

Biostatistics provides the analytical engine for translating field observations into scientific evidence. Wildlife veterinarians need not be statisticians, but they must understand the principles underlying the methods used to analyze their data and evaluate published research. Selecting appropriate methods, accounting for the hierarchical and imperfect nature of wildlife data, and reporting results transparently are hallmarks of rigorous wildlife veterinary science.
