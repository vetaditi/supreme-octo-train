# Post-Release Monitoring

## Overview

Post-release monitoring is the systematic collection of data on rehabilitated wildlife after return to the wild. Without monitoring, the success or failure of rehabilitation efforts remains unknown, and the field cannot advance evidence-based practice. Monitoring data inform survival estimates, identify causes of post-release mortality, evaluate behavioral reintegration, and guide improvements to rehabilitation protocols. This chapter covers telemetry and marking methods, monitoring protocols, data management, and metrics for defining success.

## Telemetry Methods

Telemetry provides continuous or periodic location data on released animals, enabling assessment of movement, habitat use, survival, and behavior without recapture.

### Comparison of Telemetry Technologies

| Technology | Signal Type | Weight Range | Battery Life | Detection Range | Data Resolution | Relative Cost |
|-----------|------------|-------------|-------------|----------------|----------------|--------------|
| VHF radio transmitter | Radio frequency | 0.5–50 g | 3–36 months | 1–15 km (ground); 50+ km (aerial) | Point locations during tracking sessions | Low |
| GPS logger | Satellite fix stored on board | 5–500 g | 1–24 months | Requires recapture or proximity download | High (programmed fix intervals) | Moderate |
| GPS-GSM transmitter | GPS fix transmitted via cellular | 15–500 g | 1–36 months | Wherever cellular coverage exists | High; near real-time | Moderate–High |
| Satellite (Argos/PTT) | Doppler shift via Argos satellites | 5–200 g | 2–36 months | Global | Moderate (150 m–1.5 km accuracy) | High |
| GPS-Argos hybrid | GPS fix relayed via satellite | 20–500 g | 1–36 months | Global | High (GPS accuracy with global relay) | High |
| Geolocator (light-level) | Ambient light recording | 0.3–2 g | 6–24 months | Requires recapture | Low (latitude +/- 200 km) | Low |
| Acoustic telemetry | Ultrasonic or coded pings | 0.2–30 g | 1–36 months | Receiver-dependent (100 m–1 km) | High within receiver array | Moderate |

### Transmitter Selection Guidelines

- **Weight rule** — transmitters must not exceed 3% of body mass for birds and 5% for mammals; lighter is always preferred
- **Attachment method** — backpack harness (raptors, waterfowl), leg-loop harness (passerines), glue-on (small birds, bats), subcutaneous implant (reptiles, amphibians), epoxy mount (chelonians), fin/flipper attachment (marine species)
- **Duty cycle** — program GPS units to balance data resolution with battery longevity; more frequent fixes drain batteries faster
- **Data retrieval** — remote download (GSM, satellite, Bluetooth proximity) is strongly preferred over units requiring recapture
- **Environmental durability** — saltwater, UV exposure, temperature extremes, and physical abrasion must be considered for housing material and antenna design

### VHF Radio Tracking Protocol

1. **Pre-release calibration** — test transmitter signal strength and pulse rate; record frequency to nearest 0.001 MHz
2. **Initial tracking** — daily tracking for the first 7-14 days post-release to establish movement patterns and confirm survival
3. **Systematic surveys** — after initial period, track at regular intervals (2-3 times per week) using triangulation from a minimum of three bearings
4. **Mortality signal detection** — most VHF transmitters include a mortality sensor that doubles the pulse rate after a preset period of inactivity (typically 8-12 hours); investigate all mortality signals within 24 hours
5. **Aerial surveys** — fixed-wing aircraft or helicopter tracking for wide-ranging species; conduct at regular intervals to relocate animals that have moved beyond ground-tracking range

## Marking Techniques

Marking enables individual identification during visual resighting, recapture, or recovery without reliance on active telemetry.

### Marking Methods by Taxon

| Method | Taxa | Duration | Pros | Cons |
|--------|------|----------|------|------|
| Metal leg bands (USGS BBL) | Birds | Permanent | Standardized; federal database; recoverable post-mortem | Requires recapture or recovery for reading; leg injury risk in some species |
| Color bands/flags | Birds | 1–5 years | Field-readable at distance; individual color combinations | Fading, loss, misreading; behavioral effects possible |
| PIT tags (passive integrated transponder) | All vertebrates | Permanent | Unique ID; no battery; minimal tissue reaction | Requires scanner at close range (< 15 cm); migration through tissue |
| Ear tags | Mammals | 1–5 years | Inexpensive; field-readable | Tag loss; ear tearing; infection risk |
| Lip tattoo / ear tattoo | Mammals | Permanent | Permanent; no external hardware | Requires recapture to read; fading over time |
| Flipper tags | Marine mammals, sea turtles | 1–10 years | Standard method; large databases | Tag loss; tissue reaction; entanglement risk |
| Toe clipping | Amphibians, small reptiles | Permanent | Traditional; minimal equipment | Ethical concerns; limited combinations; affects locomotion |
| Visible implant elastomer (VIE) | Amphibians, fish, small reptiles | 1–5 years | Minimally invasive; field-readable under UV | Limited color combinations; migration possible |
| Temporary dye/paint marking | All taxa | Days to weeks | Non-invasive; inexpensive; immediate visibility | Short duration; may affect thermoregulation or camouflage |
| Carapace notching/drilling | Chelonians | Permanent | Permanent; unique codes; field-readable | Invasive; shell healing varies; limited to chelonians |
| Photo identification | Cetaceans, large mammals, sharks, manta rays | Permanent (natural markings) | Non-invasive; large databases | Requires photographic effort; not all individuals distinguishable |

### PIT Tag Implantation Protocol

1. **Tag selection** — use ISO-compliant (134.2 kHz) tags for international database compatibility; 12 mm tags for most species, 8 mm for small animals
2. **Implantation site** — subcutaneous in left dorsal shoulder (mammals), left pectoral muscle (birds), left hind leg (reptiles and amphibians); follow species-specific guidelines
3. **Sterile technique** — prepare skin with chlorhexidine or alcohol; use sterile needle applicator; seal injection site with tissue adhesive if needed
4. **Verification** — scan immediately after implantation to confirm tag function; record 15-digit unique identification number
5. **Registration** — register tag number with appropriate database (e.g., AVID, HomeAgain for research use; species-specific databases)

## Survival Analysis

### Monitoring Framework for Survival Estimation

| Time Period | Monitoring Frequency | Primary Objective |
|-------------|---------------------|-------------------|
| Days 1–14 | Daily (telemetry or visual) | Detect immediate post-release mortality; evaluate site fidelity |
| Weeks 3–8 | 2–3 times per week | Assess medium-term survival; document movement patterns |
| Months 3–6 | Weekly to biweekly | Evaluate seasonal survival; document habitat use |
| Months 6–12 | Monthly | Estimate annual survival; compare to wild cohort |
| Year 2+ | Quarterly or opportunistic | Long-term survival; reproductive success; population integration |

### Analytical Approaches

- **Kaplan-Meier survival estimates** — non-parametric method suitable for small sample sizes; accommodates censored data (animals lost to follow-up or transmitter failure)
- **Cox proportional hazards models** — evaluate effects of covariates (species, injury type, time in captivity, BCS at release, season) on survival probability
- **Known-fate models** — in Program MARK or equivalent; use regular telemetry encounters to estimate survival intervals
- **Return rate analysis** — for banded or tagged animals; compare return rates of rehabilitated versus wild-banded individuals at known sites
- **Carcass recovery analysis** — systematic recording and analysis of all recovered carcasses with bands, tags, or transmitters

### Interpreting Mortality Events

When a mortality signal is detected or a carcass is recovered:

1. **Locate the carcass or transmitter** — navigate to the signal source; record GPS coordinates
2. **Scene assessment** — document the environment, carcass position, scavenging evidence, and potential cause of death
3. **Carcass recovery** — collect the carcass for necropsy if in suitable condition; follow chain-of-custody procedures for forensic cases
4. **Necropsy** — determine cause of death (predation, starvation, disease, collision, poisoning, unknown)
5. **Data recording** — enter date of death, cause of death, days post-release, and location into the monitoring database

## Behavioral Monitoring

### Key Behavioral Indicators of Successful Reintegration

| Behavior | Observation Method | Success Indicator |
|----------|-------------------|-------------------|
| Independent foraging | Direct observation; telemetry at known foraging sites | Regular use of natural food sources; weight maintenance |
| Social integration | Visual observation of interactions with conspecifics | Flock/group membership; pair formation; absence of persistent isolation |
| Territory establishment | Telemetry home range analysis; vocalization surveys | Defended territory within species-typical home range size |
| Breeding activity | Nest monitoring; behavioral observation | Nest building, egg-laying, incubation, or mate attendance |
| Appropriate habitat use | Telemetry overlay on habitat maps | Use of species-typical habitat; avoidance of anthropogenic areas |
| Predator avoidance | Survival data; behavioral observation | No evidence of naive behavior toward predators |
| Migration | Telemetry tracking through migration corridor | Successful departure, stopover use, and arrival at destination |

## Health Assessment Recapture Protocols

Recapture for health assessment should be conducted only when the information gained justifies the stress and risk to the animal. Planned recapture events are most appropriate for long-term studies and threatened species.

### Recapture Decision Criteria

- Animal shows visible signs of morbidity (lethargy, emaciation, abnormal behavior)
- Scheduled health check as part of a formal post-release monitoring protocol (e.g., translocated endangered species)
- Transmitter removal or replacement is needed
- Regulatory requirement for health certification

### Recapture Health Assessment Protocol

1. **Capture** — use species-appropriate method (mist net, trap, dart) minimizing pursuit time and stress
2. **Physical examination** — body weight, BCS, hydration status, wound assessment, ectoparasite load
3. **Blood sampling** — minimum database: PCV, total protein, blood smear for hemoparasites; expand panel as indicated
4. **Sample collection** — swabs (cloacal, oropharyngeal) for pathogen screening as indicated
5. **Transmitter/tag check** — inspect attachment, battery status, skin/feather condition at attachment site; replace if needed
6. **Release** — immediate release at capture site following assessment; minimize handling time to under 30 minutes

## Data Management

### Essential Data Fields for Post-Release Monitoring Database

| Category | Fields |
|----------|--------|
| Individual ID | Species, band/tag/PIT number, case number, sex, age class |
| Release data | Release date, GPS location, release method (soft/hard), BCS and weight at release |
| Telemetry data | Date, time, GPS coordinates, activity status, signal quality |
| Resighting data | Date, time, location, observer, behavior noted, photo if possible |
| Mortality data | Date found, GPS location, condition of carcass, cause of death, necropsy results |
| Recapture data | Date, weight, BCS, health findings, samples collected |
| Reproductive data | Nest location, clutch/litter size, hatching/birth success, fledging/weaning |

### Database Standards

- **Unique identifiers** — every individual receives a unique alphanumeric code linked across all data tables
- **Standardized terminology** — use controlled vocabularies for species names (follow ITIS), location formats (decimal degrees, WGS84), and cause-of-death categories
- **Data validation** — implement range checks, required fields, and duplicate detection at the point of entry
- **Backup protocol** — automated daily backup to a secure off-site server; maintain version control
- **Data sharing** — contribute survival and recovery data to national databases (USGS Bird Banding Laboratory, NOAA marine mammal stranding network, state wildlife agencies)

## Success Metrics

Defining rehabilitation success requires explicit, measurable criteria established before release.

### Tiered Success Framework

| Tier | Metric | Definition | Minimum Threshold |
|------|--------|-----------|-------------------|
| Tier 1 | Short-term survival | Alive at 30 days post-release | ≥ 50% of released cohort |
| Tier 2 | Medium-term survival | Alive at 6 months post-release | ≥ 30% of released cohort (comparable to wild juvenile survival) |
| Tier 3 | Annual survival | Alive at 12 months post-release | Within range of published wild survival estimates for species and age class |
| Tier 4 | Reproductive success | Confirmed breeding attempt or successful reproduction | Documentation in at least some released individuals |
| Tier 5 | Population contribution | Offspring recruited into breeding population | Long-term genetic or demographic contribution documented |

### Benchmarking Against Wild Populations

The ultimate measure of rehabilitation success is whether released animals achieve survival and reproductive rates comparable to their wild counterparts. Published survival estimates for wild populations of the same species, age class, and region serve as the benchmark. If rehabilitated animals consistently show significantly lower survival than wild cohorts, the rehabilitation protocol requires critical evaluation — either the release criteria are insufficient, the rehabilitation process is causing lasting impairment, or the species is not a good candidate for rehabilitation.

### Reporting and Program Evaluation

- **Annual outcome reports** — summarize release numbers, survival rates, causes of mortality, and reproductive outcomes by species
- **Multi-year trend analysis** — track changes in outcomes over time to evaluate protocol improvements
- **Cost-per-successful-release** — calculate total resources expended per animal achieving Tier 2 or higher success
- **Publication** — contribute findings to peer-reviewed literature and rehabilitation conferences to advance the collective evidence base
