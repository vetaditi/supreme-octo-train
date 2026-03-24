# Epidemiology and Disease Modeling

## Overview

Wildlife epidemiology adapts the principles and tools of human and veterinary epidemiology to the unique challenges of studying disease in free-ranging animal populations. These challenges include difficulty in detecting cases, unknown population sizes, limited ability to conduct controlled experiments, and the complex ecological interactions that drive disease dynamics. Mathematical modeling is a cornerstone of wildlife epidemiology, providing frameworks to understand transmission, predict outbreaks, and evaluate intervention strategies.

## Compartmental Disease Models

### SIR Model

The Susceptible-Infected-Recovered (SIR) model is the foundational framework for modeling infectious disease dynamics. It divides the population into three compartments:

- **S (Susceptible)**: Individuals who can become infected
- **I (Infected)**: Individuals who are currently infected and infectious
- **R (Recovered)**: Individuals who have recovered and are immune

The basic SIR equations:

```
dS/dt = -beta * S * I / N
dI/dt = beta * S * I / N - gamma * I
dR/dt = gamma * I
```

Where beta is the transmission rate, gamma is the recovery rate, and N is the total population size.

**Wildlife applications**: The SIR model applies when infection confers lasting immunity. Examples include canine distemper in wild carnivores and many viral infections where survivors develop durable antibodies.

### SIS Model

The Susceptible-Infected-Susceptible (SIS) model applies when recovery does not confer lasting immunity:

```
dS/dt = -beta * S * I / N + gamma * I
dI/dt = beta * S * I / N - gamma * I
```

**Wildlife applications**: Many bacterial infections and parasitic diseases follow SIS dynamics. Examples include brucellosis in some wildlife populations and many helminth infections where reinfection is common.

### SEIR Model

The SEIR model adds an Exposed (latent) compartment for pathogens with a significant incubation period:

- **E (Exposed)**: Infected but not yet infectious

```
dS/dt = -beta * S * I / N
dE/dt = beta * S * I / N - sigma * E
dI/dt = sigma * E - gamma * I
dR/dt = gamma * I
```

Where sigma is the rate of progression from exposed to infectious (1/sigma = mean latent period).

**Wildlife applications**: Rabies (long and variable incubation period), tuberculosis, and many viral diseases with distinct latent periods.

### Model Extensions for Wildlife

Standard compartmental models often require modification for wildlife applications:

| Extension | Rationale | Example |
|---|---|---|
| Age structure | Disease susceptibility varies with age | Chronic wasting disease in cervids |
| Seasonal forcing | Transmission varies with season | Avian influenza in waterfowl |
| Spatial structure | Populations are not well-mixed | Bovine TB in badgers |
| Multi-host models | Pathogen circulates among multiple species | West Nile virus |
| Environmental reservoir | Pathogen persists outside hosts | Anthrax spores in soil |
| Carrier states | Recovered animals remain infectious | Salmonellosis in reptiles |
| Vertical transmission | Parent-to-offspring transmission | Retroviral infections |
| Vector dynamics | Arthropod vectors mediate transmission | Avian malaria |

## R0 Estimation in Wildlife

### Definition and Significance

The basic reproduction number (R0) represents the average number of secondary infections produced by a single infected individual in a completely susceptible population. It is the single most important parameter in infectious disease epidemiology:

- **R0 > 1**: The disease can invade and spread in the population
- **R0 = 1**: The disease is at an endemic equilibrium
- **R0 < 1**: The disease will fade out

### Estimation Methods

Estimating R0 in wildlife populations is challenging due to limited data. Common approaches include:

**From epidemic curve data**:
- Exponential growth rate method: R0 = 1 + r * D, where r is the initial growth rate and D is the mean infectious period
- Maximum likelihood fitting of transmission models to incidence data

**From seroprevalence data**:
- For endemic infections: R0 = 1 / (1 - p), where p is the equilibrium seroprevalence
- Requires assumptions about population mixing and stable endemic state

**From contact data**:
- Network-based approaches using telemetry or proximity logger data
- R0 = beta * c * D, where c is the contact rate and D is the infectious duration

**From outbreak final size**:
- The final size equation relates R0 to the proportion of the population ultimately infected

### Challenges in Wildlife R0 Estimation

- Difficulty distinguishing new infections from old infections
- Unknown population sizes and structures
- Variable contact rates across seasons and habitats
- Multi-host systems complicate interpretation
- Limited ability to detect early epidemic growth

## Population Viability Analysis Incorporating Disease

### PVA Fundamentals

Population Viability Analysis (PVA) uses demographic models to project population trajectories and estimate extinction risk. Incorporating disease into PVA is essential when pathogens represent a significant threat to population persistence.

### Integration Approaches

**Scenario-based approach**: Run PVA models with and without disease events of defined frequency and severity. Compare extinction probabilities and population trajectories.

**Coupled demographic-epidemiological models**: Link disease transmission models directly to demographic models so that disease prevalence dynamically affects survival and reproduction rates.

**Key parameters for disease-PVA integration**:
- Disease-induced mortality rate (virulence)
- Disease effects on fecundity
- Outbreak frequency and duration
- Relationship between population density and disease transmission
- Potential for disease-mediated Allee effects

### Software Tools

- **Vortex**: The most widely used PVA software in conservation; can incorporate disease as catastrophic events or through linked epidemiological modules
- **RAMAS**: Spatial PVA with capacity for disease incorporation
- **Custom R/Python models**: Increasingly used for complex disease-demography coupling

## Stochastic Modeling

### Why Stochasticity Matters

Deterministic models describe average behavior, but wildlife populations are subject to multiple sources of randomness that can critically affect outcomes, especially in small populations:

- **Demographic stochasticity**: Random variation in individual birth and death events. Dominant in small populations.
- **Environmental stochasticity**: Year-to-year variation in vital rates driven by environmental fluctuation.
- **Disease stochasticity**: Random variation in transmission events, outbreak timing, and severity.

### Stochastic Model Approaches

**Individual-based models (IBMs)**: Track the fate of each individual animal. Computationally intensive but can incorporate individual heterogeneity in susceptibility, behavior, and spatial location.

**Stochastic differential equations**: Add noise terms to deterministic ODE models. Mathematically tractable but may not capture all relevant sources of variation.

**Markov chain models**: Transition probabilities between disease states are modeled as random processes. Useful for discrete time steps.

**Tau-leaping and Gillespie algorithms**: Efficient simulation methods for stochastic compartmental models.

### Interpreting Stochastic Results

- Run sufficient iterations (typically 1000+) to characterize the distribution of outcomes
- Report median trajectories and confidence/prediction intervals rather than single projections
- Probability of extinction is often more informative than mean population size
- Quasi-extinction thresholds (population falling below a critical size) may be more practical than true extinction

## Transmission Dynamics

### Density-Dependent Transmission

In density-dependent (mass action) transmission, the force of infection increases with host population density:

```
Force of infection = beta * I / Area
```

This means that as population density increases, each individual has more contacts and disease transmission accelerates. Implications include:

- **Threshold density**: There exists a critical host density below which the pathogen cannot persist (NT)
- **Population regulation**: Disease can regulate host populations around the threshold density
- **Management implication**: Reducing host density (through culling, for example) can theoretically control disease

**Examples**: Many directly transmitted respiratory and contact-transmitted diseases in gregarious species. Bovine tuberculosis in high-density badger populations.

### Frequency-Dependent Transmission

In frequency-dependent transmission, the force of infection depends on the proportion (not absolute number) of infectious individuals:

```
Force of infection = beta * I / N
```

Key characteristics:

- **No threshold density**: The pathogen can persist regardless of population density
- **Cannot be controlled by density reduction alone**: Culling may be ineffective or counterproductive
- **Particularly dangerous for small populations**: Can drive populations to extinction because transmission efficiency does not decline as the population shrinks

**Examples**: Sexually transmitted diseases, diseases transmitted through territorial behavior, and transmissible cancers (devil facial tumor disease).

### Mixed Transmission Modes

Many wildlife diseases exhibit elements of both density-dependent and frequency-dependent transmission, or the mode may shift depending on ecological context. The generalized transmission function provides a flexible framework:

```
Force of infection = beta * I^p * S^q / N^r
```

Where the exponents p, q, and r can be estimated from data to determine the best-fitting transmission mode.

## Metapopulation Disease Dynamics

### Spatial Structure and Disease

Most wildlife populations are not panmictic but exist as metapopulations: networks of subpopulations connected by dispersal. This spatial structure profoundly affects disease dynamics:

- **Asynchronous dynamics**: Disease may be present in some subpopulations and absent from others at any given time
- **Rescue effect**: Healthy subpopulations can recolonize patches where disease has caused local extinction
- **Stepping-stone spread**: Disease may spread sequentially through connected subpopulations
- **Barrier effects**: Gaps in connectivity can slow or prevent disease spread

### Metapopulation Disease Models

**Patch occupancy models**: Track whether each subpopulation is occupied, unoccupied, or infected. The Levins metapopulation model can be extended to include disease states.

**Network models**: Represent subpopulations as nodes and dispersal routes as edges. Disease spread depends on network topology (connectivity, clustering, path length).

**Spatially explicit simulation models**: Place subpopulations in realistic geographic space with distance-dependent dispersal. Can incorporate landscape features that affect connectivity.

### Key Parameters

- **Dispersal rate**: Frequency and distance of inter-patch movement
- **Patch size**: Determines local population dynamics and extinction probability
- **Connectivity**: Number and strength of links between patches
- **Pathogen persistence in patches**: How long a pathogen can maintain transmission in a local population before stochastic fadeout
- **Recolonization rate**: How quickly empty patches are recolonized from source populations

### Management Implications

Metapopulation structure creates both challenges and opportunities for disease management:

- **Corridor management**: Maintaining connectivity supports population viability but may also facilitate disease spread. This creates a fundamental tension in conservation management.
- **Vaccination barriers**: Strategic vaccination of subpopulations at key network positions can prevent spread without treating the entire metapopulation.
- **Surveillance prioritization**: Monitoring effort should focus on highly connected subpopulations and likely introduction points.
- **Quarantine zones**: Temporarily reducing connectivity around infected subpopulations may contain outbreaks.

## Data Collection for Epidemiological Modeling

### Essential Data Types

- **Incidence/prevalence data**: From active surveillance, passive surveillance, or opportunistic sampling
- **Demographic data**: Population size, age structure, survival rates, fecundity
- **Contact data**: Direct observation, proximity loggers, GPS telemetry
- **Spatial data**: Individual locations, habitat maps, landscape features
- **Temporal data**: Seasonal patterns, outbreak timelines, long-term trends
- **Host community data**: Species composition, relative abundance, interspecific interactions

### Surveillance System Design

Effective disease surveillance in wildlife requires balancing coverage with feasibility:

- **Active surveillance**: Systematic sampling of apparently healthy animals. Provides unbiased prevalence estimates but is resource-intensive.
- **Passive surveillance**: Testing of animals found dead, sick, or hunter-harvested. Biased but cost-effective and can detect unusual mortality events.
- **Sentinel surveillance**: Monitoring selected indicator species or populations for early warning of disease emergence.
- **Syndromic surveillance**: Monitoring for clinical syndromes rather than specific pathogens. Useful for detecting novel or unexpected threats.

### Model Selection and Validation

- Use AIC, BIC, or DIC for model comparison
- Validate models against independent data when possible
- Sensitivity analysis to identify parameters with the greatest influence on model outcomes
- Present uncertainty explicitly in model projections
- Communicate model limitations clearly to decision-makers
