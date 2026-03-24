# Data Management for Wildlife Research

## Introduction

Effective data management is the backbone of reliable, reproducible wildlife research. The best study design and most sophisticated statistical analysis are worthless if the underlying data are poorly collected, inadequately documented, or improperly stored. Wildlife research poses particular data management challenges: field conditions are harsh, datasets span multiple taxa and locations, long-term projects require data to remain usable across personnel changes, and increasingly, data must be shared across institutions and borders. This chapter covers practical approaches to managing wildlife health data throughout its lifecycle.

## Field Data Collection

### Mobile Data Collection Applications

Modern field data collection has largely transitioned from paper datasheets to mobile devices, offering significant advantages:

| Application | Platform | Key Features |
|-------------|----------|-------------|
| KoBoToolbox | Web, Android, iOS | Open-source, offline capability, skip logic, GPS integration |
| ODK (Open Data Kit) | Android | Open-source, highly customizable, offline-capable |
| Survey123 (ArcGIS) | Cross-platform | GIS integration, conditional logic, photo capture |
| Fulcrum | Cross-platform | Commercial; robust offline mode, barcode scanning |
| EpiCollect5 | Web, Android, iOS | Free, designed for epidemiological data collection |
| Cybertracker | Android | Designed for wildlife monitoring, icon-based interface for non-literate users |

**Best practices for mobile data collection:**

- Design forms with standardized fields, drop-down menus, and validation rules to minimize entry errors
- Include automatic GPS coordinate capture with every record
- Build in required fields for critical variables to prevent missing data
- Use barcode or QR code scanning for sample tracking
- Test forms thoroughly under field conditions before deployment
- Maintain paper backup datasheets for equipment failure scenarios
- Synchronize data to a central server as soon as connectivity allows

### GPS Loggers and Telemetry Data

Wildlife tracking generates large, complex datasets:

- **GPS collars and tags**: Record location at programmed intervals; data volume scales rapidly (e.g., hourly fixes for 100 animals over one year generates approximately 876,000 location records)
- **Satellite telemetry (Argos, Iridium)**: Lower spatial precision than GPS but enables tracking in remote areas without data retrieval visits
- **VHF telemetry**: Requires manual triangulation; lower data volume but still requires systematic recording
- **Accelerometers and activity sensors**: Generate very high-frequency data for behavior classification

**Data management considerations:**
- Standardize coordinate reference systems (use WGS84/EPSG:4326 as default)
- Document collar/tag deployment metadata (animal ID, species, sex, age, deployment date, collar model, programmed schedule)
- Implement automated data downloads where possible (satellite-linked systems, base station downloads)
- Apply screening filters for erroneous locations (unrealistic movement speeds, locations far from known range)
- Store raw and filtered datasets separately; never overwrite raw data

### Biological Sample Tracking

Managing the chain of custody for biological samples requires systematic approaches:

- **Unique sample identifiers**: Assign unique IDs following a consistent convention (e.g., SPECIES-SITE-DATE-INDIVIDUAL-SAMPLETYPE)
- **Sample logs**: Record collection date, time, location, collector, sample type, storage conditions, and any processing applied
- **Freezer inventories**: Maintain updated inventories of stored samples with box positions
- **Aliquoting protocols**: When samples are divided, each aliquot receives a linked sub-identifier
- **Transfer documentation**: Log all sample transfers between personnel, institutions, or laboratories with dates and tracking numbers

## Database Design

### Relational Database Principles

Wildlife health data is naturally relational, with entities that connect across tables:

- **Individual animals**: Demographics, marking data, morphometrics
- **Capture events**: Date, location, method, personnel, conditions
- **Health assessments**: Clinical findings, body condition, samples collected
- **Diagnostic results**: Test type, result, date, laboratory
- **Location data**: GPS coordinates, habitat description, site characteristics
- **Environmental data**: Temperature, precipitation, habitat metrics

**Design guidelines:**

- Use a relational database management system (PostgreSQL, MySQL, SQLite for simpler applications)
- Normalize data to reduce redundancy (each fact stored once; linked by keys)
- Define primary keys for every table and foreign keys for relationships
- Use consistent data types for each field (dates as ISO 8601, coordinates as decimal degrees)
- Implement referential integrity constraints to prevent orphaned records
- Create data dictionaries documenting every table, field, data type, and allowable values

### Common Database Platforms

| Platform | Scale | Cost | Strengths |
|----------|-------|------|-----------|
| SQLite | Small-medium | Free | Self-contained file, no server needed |
| PostgreSQL (+ PostGIS) | Medium-large | Free | Robust, spatial capability |
| Microsoft Access | Small-medium | Licensed | Familiar interface, forms and reports |
| MySQL/MariaDB | Medium-large | Free | Widely used, well-documented |
| Airtable | Small-medium | Freemium | Low-code, collaborative |
| REDCap | Research-specific | Free for academic | Designed for research data capture, audit trails |

## Data Quality Assurance

### Prevention (During Collection)

- Constrained input fields (drop-down menus, valid ranges, required fields)
- Real-time validation rules in mobile collection apps
- Standardized protocols with clear instructions and decision trees
- Training and calibration of field personnel
- Inter-observer reliability assessments for subjective measurements (body condition scoring, lesion grading)

### Detection (After Collection)

- **Range checks**: Flag values outside biologically plausible ranges (e.g., body temperature > 45C for a mammal)
- **Consistency checks**: Cross-validate related fields (e.g., juvenile age class should not have adult body mass)
- **Duplicate detection**: Identify and resolve duplicate records
- **Completeness assessment**: Quantify and document missing data rates for each variable
- **Temporal consistency**: Check that sequential events (capture, sample, result) have logical temporal ordering
- **Spatial consistency**: Verify that locations fall within expected geographic ranges

### Documentation

- Maintain a data quality log documenting all errors found, corrections made, and the rationale for each correction
- Preserve the original uncorrected data alongside the corrected dataset
- Version datasets (v1.0, v1.1, etc.) with changelogs documenting modifications

## Standardized Data Formats

### Darwin Core

The biodiversity data standard used by GBIF and many national biodiversity information facilities:

- Provides standardized terms for occurrence, event, location, and taxon data
- Enables interoperability across datasets and platforms
- Core terms include: scientificName, decimalLatitude, decimalLongitude, eventDate, basisOfRecord, occurrenceStatus

### Ecological Metadata Language (EML)

A standard for documenting ecological datasets:

- Describes who collected the data, when, where, how, and why
- Includes information on sampling methods, quality control, and access policies
- Machine-readable XML format; can be created using R packages (`EML`, `emld`)

### Veterinary-Specific Standards

- **ADIS (Animal Disease Information System)**: Standardized disease reporting formats used by WOAH
- **HL7/FHIR**: Health data exchange standards adapted for veterinary diagnostic data
- **LOINC**: Standardized laboratory test codes applicable to veterinary diagnostics

## Data Sharing

### Global Biodiversity Information Facility (GBIF)

GBIF is the primary global platform for sharing biodiversity occurrence data:

- Free and open access to over 2 billion records from thousands of institutions
- Wildlife health data (especially disease occurrence) can be published through GBIF using Darwin Core standards
- Publishing involves registering as a data publisher, formatting data, and uploading through the Integrated Publishing Toolkit (IPT)

### Wildlife Health Databases

| Database | Scope | Access |
|----------|-------|--------|
| WHISPers (USGS-NWHC) | US wildlife morbidity/mortality events | Public |
| WAHIS (WOAH) | Global reportable animal diseases | Public |
| Canadian Wildlife Health Information Network (CWHIN) | Canadian wildlife health data | Restricted |
| Surveillance of Wildlife Diseases in Northern Europe (SWIN) | Nordic wildlife health | Collaborative |
| PREDICT Pathogen Database | Global wildlife virus surveillance | Archived |

### Principles of FAIR Data

Modern data sharing follows the FAIR principles:

- **Findable**: Data should have persistent identifiers (DOIs) and be indexed in searchable registries
- **Accessible**: Data should be retrievable via standard protocols, with clear access conditions
- **Interoperable**: Data should use standardized formats and vocabularies to enable integration with other datasets
- **Reusable**: Data should be well-documented, with clear provenance and usage licenses

## Data Ethics and Privacy

### Sensitive Location Data

Wildlife research generates location data that can be misused:

- **Endangered species locations**: Poaching risk from disclosed nest sites, den locations, or habitats of high-value species
- **Disease occurrence data**: Premature disclosure may trigger inappropriate culling or public panic
- **Private land data**: Landowner privacy must be respected

**Mitigation strategies:**
- Generalize coordinates (reduce precision to 10 km grid cells) for public datasets
- Embargo sensitive data for agreed periods
- Use access-controlled databases for high-sensitivity data
- Follow institutional and national guidelines for sensitive species data (e.g., GBIF data sensitivity best practices)

### Human Subjects Data

One Health research that involves human participants (e.g., surveys of communities near wildlife disease hotspots) requires:

- Institutional Review Board (IRB) or Ethics Committee approval
- Informed consent procedures
- Data de-identification and secure storage
- Compliance with applicable data protection regulations (e.g., GDPR in Europe)

### Indigenous Data Sovereignty

Research involving indigenous lands, species, or knowledge systems must respect indigenous data sovereignty principles:

- **CARE Principles**: Collective benefit, Authority to control, Responsibility, Ethics
- Free, prior, and informed consent from indigenous communities
- Data governance agreements that ensure indigenous communities retain control over their data
- Recognition of indigenous knowledge as intellectual property

## Reproducible Research Practices

### Version Control

- Use version control systems (Git) for analysis code and documentation
- Platforms such as GitHub or GitLab provide collaborative version control with issue tracking
- Tag releases of code corresponding to manuscript submissions and publications

### Literate Programming

- R Markdown, Quarto, or Jupyter notebooks combine narrative text, code, and results in a single document
- Ensures that analyses are fully documented and reproducible
- Facilitates peer review of both methods and results

### Containerization and Environment Management

- Document computational environments using `renv` (R) or `conda` (Python) to capture package versions
- Docker containers provide fully reproducible computational environments
- Ensures analyses can be reproduced years later despite software updates

### Data Archiving

- Archive datasets in long-term repositories with DOIs:
  - **Dryad**: General-purpose data repository
  - **Zenodo**: CERN-hosted, integrates with GitHub, free
  - **Figshare**: Free for individual researchers
  - **Movebank**: Specialized for animal movement data
  - **GenBank/NCBI**: Sequence data
- Follow journal data availability policies
- Include metadata sufficient for independent reuse

### Code Sharing

- Share analysis code alongside publications
- Comment code thoroughly
- Include a README describing the code structure, dependencies, and how to run the analysis
- Use permissive open-source licenses (MIT, Apache 2.0) for code

## Data Management Plans

Most funding agencies now require data management plans (DMPs) as part of grant applications:

**Key components:**
1. **Data description**: Types, formats, and estimated volume of data to be generated
2. **Standards**: Data and metadata standards to be used
3. **Access and sharing**: How, when, and where data will be made available
4. **Preservation**: Long-term storage and archiving plan
5. **Responsibilities**: Who is responsible for data management activities
6. **Budget**: Resources allocated for data management

**Tools:**
- DMPTool (dmptool.org): Free, provides templates for major funder requirements
- DMPonline (dmponline.dcc.ac.uk): UK-based equivalent

## Summary

Data management may lack the excitement of fieldwork or the elegance of statistical analysis, but it is the infrastructure on which all other research activities depend. Investing time in proper data collection tools, database design, quality assurance, standardized formats, ethical data handling, and reproducible research practices pays dividends throughout the research lifecycle and ensures that hard-won wildlife health data remain valuable for years and decades to come.
