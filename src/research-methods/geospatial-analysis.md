# Geospatial Analysis for Wildlife Health

## Introduction

Geography is inseparable from wildlife health. Where an animal lives, moves, feeds, and reproduces determines its exposure to pathogens, parasites, contaminants, and environmental stressors. Geospatial analysis provides the tools to capture, analyze, and visualize these spatial dimensions of wildlife health, transforming location data into ecological and epidemiological insight. This chapter covers the key geospatial methods and tools relevant to wildlife veterinary research and practice.

## GIS Fundamentals for Wildlife Health

### What Is a Geographic Information System?

A GIS is a system for capturing, storing, analyzing, and displaying geographically referenced data. For wildlife health applications, GIS integrates:

- **Animal locations**: GPS telemetry, capture sites, mortality locations, sightings
- **Health data**: Disease status, sample results, body condition, contaminant levels
- **Environmental layers**: Land cover, elevation, hydrology, climate, human infrastructure
- **Administrative boundaries**: Protected areas, management units, jurisdictions

### Data Models

| Model | Description | Wildlife Health Examples |
|-------|-------------|----------------------|
| Vector (points) | Discrete locations | Animal captures, mortality events, sample collection sites |
| Vector (lines) | Linear features | Animal movement paths, rivers, roads, fence lines |
| Vector (polygons) | Bounded areas | Home ranges, protected areas, outbreak zones, habitat patches |
| Raster | Grid of cells with values | Elevation, temperature, NDVI, land cover, precipitation |

### Coordinate Reference Systems

- All spatial data must be associated with a defined coordinate reference system (CRS)
- **Geographic CRS** (e.g., WGS84, EPSG:4326): Latitude/longitude in degrees; appropriate for global datasets
- **Projected CRS** (e.g., UTM zones, Albers Equal Area): Meters or feet; necessary for distance and area calculations
- Mismatched CRS between datasets is a common source of error; always verify and transform as needed

### Essential GIS Operations

- **Buffering**: Create zones around features (e.g., 5 km buffer around a disease outbreak site)
- **Overlay/intersection**: Combine layers to identify relationships (e.g., animal locations within specific land cover types)
- **Spatial join**: Attach attributes from one layer to another based on spatial relationships
- **Clipping**: Extract data within a defined area of interest
- **Raster extraction**: Extract environmental values at point locations (e.g., elevation, temperature at each animal capture site)

## Remote Sensing for Wildlife Health

### Key Remote Sensing Products

#### Normalized Difference Vegetation Index (NDVI)

NDVI quantifies vegetation greenness and photosynthetic activity:

- **Calculation**: NDVI = (NIR - Red) / (NIR + Red), where NIR = near-infrared reflectance and Red = red reflectance
- **Range**: -1 to +1; higher values indicate denser, greener vegetation
- **Wildlife health applications**:
  - Proxy for forage quality and nutritional resources for herbivores
  - Predictor of body condition and reproductive success in ungulates
  - Correlate of vector habitat suitability (vegetation moisture affects tick and mosquito habitats)
  - Early warning of drought stress and associated wildlife health impacts

#### Land Cover Classification

Classified satellite imagery provides habitat maps:

- **Global products**: ESA WorldCover (10m), Copernicus Global Land Service, MODIS Land Cover
- **Applications**: Quantifying habitat composition within home ranges, mapping wildlife-livestock interface zones, identifying land use changes that alter disease risk

#### Surface Temperature

Land surface temperature (LST) from thermal satellite sensors:

- Relates to vector development rates and pathogen survival
- Identifies thermal refugia for wildlife under heat stress
- Informs models of temperature-dependent diseases

### Satellite Data Sources

| Source | Resolution | Revisit | Cost | Key Products |
|--------|-----------|---------|------|-------------|
| Landsat (USGS/NASA) | 30 m | 16 days | Free | NDVI, land cover, surface temperature |
| Sentinel-2 (ESA) | 10-20 m | 5 days | Free | NDVI, land cover, water bodies |
| MODIS (NASA) | 250-1000 m | 1-2 days | Free | NDVI, LST, fire, snow cover |
| VIIRS (NOAA) | 375-750 m | Daily | Free | Night lights, fires, sea surface temperature |
| Planet | 3-5 m | Daily | Commercial | High-resolution monitoring |

### Google Earth Engine

Google Earth Engine (GEE) provides cloud-based access to petabytes of satellite imagery and geospatial datasets:

- Free for research and non-commercial use
- JavaScript and Python APIs for automated analysis
- Enables time-series analysis over decades of satellite data
- Eliminates the need to download and process large raster datasets locally
- Particularly useful for landscape-scale and long-term environmental monitoring

## Spatial Epidemiology

### Mapping Disease Risk

Spatial epidemiology applies geographic concepts to understand disease distribution:

- **Disease mapping**: Visualize where cases occur relative to environmental features, populations, and potential sources
- **Risk surface modeling**: Use environmental covariates (climate, land cover, elevation, human population density) to predict disease risk across unsampled areas
- **Hotspot detection**: Identify areas with statistically elevated disease frequency (see cluster detection methods in the Epidemiological Tools chapter)

### Environmental Risk Factor Analysis

Relate disease occurrence to spatially explicit environmental variables:

1. Extract environmental values at case and control/random locations
2. Fit models (logistic regression, boosted regression trees, random forests) to identify significant predictors
3. Project risk across the landscape using the fitted model and environmental layers
4. Validate with independent data or cross-validation

### Movement and Disease Transmission

Animal movement data from telemetry can inform disease transmission modeling:

- Contact analysis: Identify when and where individuals are in close proximity
- Network analysis: Map social and spatial contact networks to understand transmission potential
- Corridor identification: Find movement pathways that may serve as disease transmission routes
- Interface mapping: Quantify spatial overlap between wildlife and livestock

## Home Range Analysis

### Methods

| Method | Description | Assumptions | Best For |
|--------|-------------|-------------|---------|
| Minimum Convex Polygon (MCP) | Smallest convex polygon enclosing all points | All locations are habitat | Simple comparisons; regulatory requirements |
| Kernel Density Estimation (KDE) | Probability surface based on point density | Smooth, unimodal distribution | General home range estimation |
| Local Convex Hull (LoCoH) | Union of local convex hulls around each point | Hard-boundary home ranges | Areas with sharp boundaries (coastlines, cliffs) |
| Brownian Bridge Movement Model | Accounts for temporal sequence and movement between points | Sequential locations, known measurement error | GPS telemetry data with regular fix intervals |
| Dynamic Brownian Bridge | Time-varying movement variance | Changing movement behavior over time | Long-term telemetry with behavioral shifts |
| Autocorrelated KDE (AKDE) | Accounts for spatial autocorrelation in tracking data | Continuous-time movement model | Modern GPS telemetry with frequent fixes |

### Health Applications of Home Range Analysis

- Compare home range sizes between healthy and diseased individuals
- Identify habitat types used disproportionately by infected animals
- Quantify overlap between wildlife and domestic animal ranges to assess disease transmission risk
- Assess spatial fidelity to contaminated sites (e.g., lead exposure near mine sites)

## Habitat Suitability Modeling

### Purpose

Habitat suitability models (HSMs) predict where environmental conditions are suitable for a species, pathogen, or vector:

- Inform targeted surveillance by predicting where to look for disease or host species
- Identify potential range expansion areas under climate change
- Support conservation planning by mapping critical habitat

### Modeling Approaches

- **Correlative models**: Relate known species occurrences to environmental conditions
- **Mechanistic models**: Use physiological constraints (thermal tolerance, moisture requirements) to predict suitable habitat
- **Hybrid approaches**: Combine correlative and mechanistic elements

## Species Distribution Modeling

### MaxEnt (Maximum Entropy Modeling)

MaxEnt is the most widely used species distribution modeling platform in wildlife research:

- **Input**: Presence-only occurrence data plus environmental raster layers
- **Output**: Predicted probability of presence (or relative habitat suitability) across the landscape
- **Algorithm**: Finds the distribution of maximum entropy (most uniform) subject to constraints imposed by the environmental conditions at known occurrence locations

**Best practices:**
- Use spatially thinned occurrence data to reduce sampling bias
- Select biologically meaningful environmental variables (avoid data dredging)
- Address multicollinearity among predictors
- Evaluate model performance with AUC, TSS, and Boyce index
- Use spatial cross-validation (spatially blocked) rather than random cross-validation to avoid optimistic performance estimates
- Report response curves showing how predicted suitability varies with each environmental variable

### Ensemble Modeling

Combine predictions from multiple algorithms to reduce model-specific bias:

- Fit multiple models (MaxEnt, Random Forest, GLM, BRT, GAM) to the same data
- Combine predictions using weighted averaging, committee averaging, or median
- The `biomod2` R package provides a comprehensive framework for ensemble species distribution modeling

### Applications in Wildlife Health

- Predicting geographic distribution of disease vectors under current and future climate scenarios
- Mapping overlap zones between hosts, vectors, and susceptible populations
- Identifying areas where newly emerging diseases may spread
- Guiding surveillance effort toward high-risk areas

## Disease Risk Mapping

### Integrated Risk Maps

Disease risk maps combine multiple spatial data layers to estimate spatially explicit disease risk:

**Components:**
1. **Hazard**: Where is the pathogen or vector present? (pathogen/vector distribution models)
2. **Exposure**: Where do susceptible hosts encounter the hazard? (host distribution, movement, habitat use)
3. **Vulnerability**: Where are hosts most susceptible? (body condition, immune status, population density, environmental stress)

**Construction:**
- Develop models for each component using appropriate methods
- Combine component layers through additive, multiplicative, or more complex spatial models
- Validate against independent disease occurrence data
- Update as new data become available

### Examples

- Avian influenza risk maps combining wild bird migration data, poultry density, wetland distribution, and climate suitability
- Chronic wasting disease risk maps based on deer density, habitat connectivity, and proximity to known positive sites
- Anthrax risk maps using soil pH, calcium content, flooding history, and historical outbreak records

## Geospatial Tools and Software

### QGIS

- Free, open-source GIS software
- Full-featured: vector and raster analysis, map composition, spatial database connectivity
- Extensive plugin ecosystem (including epidemiological and ecological tools)
- Active community and comprehensive documentation
- Cross-platform (Windows, macOS, Linux)

### ArcGIS

- Commercial GIS platform (ESRI)
- Industry standard in many government and academic settings
- ArcGIS Pro (desktop), ArcGIS Online (cloud-based), and specialized extensions
- Spatial Analyst, Spatial Statistics, and Geostatistical Analyst toolboxes
- Python integration (ArcPy)

### R Spatial Packages

| Package | Purpose |
|---------|---------|
| `sf` | Vector data handling (Simple Features standard) |
| `terra` | Raster data handling (successor to `raster`) |
| `tmap` | Thematic maps |
| `leaflet` | Interactive web maps |
| `adehabitatHR` | Home range analysis |
| `ctmm` | Continuous-time movement modeling and AKDE |
| `move2` | Movement data analysis framework |
| `spatstat` | Spatial point pattern analysis |
| `spdep` | Spatial dependence and autocorrelation |
| `dismo` | Species distribution modeling (including MaxEnt interface) |
| `biomod2` | Ensemble species distribution modeling |
| `rgee` | R interface to Google Earth Engine |
| `SaTScan` | Spatial and space-time cluster detection (standalone software) |

### Python Geospatial Stack

- `geopandas`: Vector data analysis
- `rasterio` / `xarray`: Raster data
- `folium`: Interactive maps
- `scikit-learn`: Machine learning for spatial prediction
- `ee` (Earth Engine Python API): Google Earth Engine access

## Practical Workflow Example

A typical geospatial workflow for wildlife disease investigation:

1. **Data compilation**: Gather disease occurrence points, animal telemetry data, environmental rasters (NDVI, elevation, temperature, land cover, hydrology)
2. **Data preparation**: Project all layers to a common CRS; clip to the study area; extract environmental values at occurrence and background points
3. **Exploratory mapping**: Visualize cases over environmental layers; identify spatial patterns
4. **Spatial analysis**: Cluster detection, home range estimation, environmental risk factor analysis
5. **Modeling**: Fit species distribution or disease risk models; evaluate performance; generate predictive maps
6. **Visualization and communication**: Produce publication-quality maps; create interactive web maps for stakeholders; summarize spatial findings in reports

## Summary

Geospatial analysis transforms wildlife health data from point observations into landscape-level understanding. By integrating animal locations, health data, and environmental information within a spatial framework, wildlife veterinarians can identify where disease risk is highest, why certain areas are affected, and where to target surveillance and intervention. Proficiency with GIS tools and spatial analysis methods is an increasingly essential competency for wildlife health professionals.
