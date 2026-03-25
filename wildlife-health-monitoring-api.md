# Wildlife Health Monitoring API Collection Documentation

A comprehensive collection for integrating wildlife health monitoring APIs including biodiversity data, animal tracking, species observations, conservation status, and environmental data.

---

## Table of Contents

- [GBIF - Biodiversity Data](#gbif---biodiversity-data)
- [iNaturalist - Wildlife Observations](#inaturalist---wildlife-observations)
- [Movebank - Animal Tracking](#movebank---animal-tracking)
- [IUCN Red List - Conservation Status](#iucn-red-list---conservation-status)
- [NASA Earthdata - Environmental Data](#nasa-earthdata---environmental-data)

---

## GBIF - Biodiversity Data

Global Biodiversity Information Facility API for species occurrence and biodiversity data. No authentication required.

### 1. Search Species Occurrences

- **Endpoint**: `GET https://api.gbif.org/v1/occurrence/search?scientificName=Panthera leo&limit=10`
- **Description**: Search for species occurrence records by scientific name.

| Name | Type | Example Value | Description |
|---|---|---|---|
| scientificName | string | Panthera leo | Scientific name |
| limit | int | 10 | Results per request |

### 2. Get Species Info

- **Endpoint**: `GET https://api.gbif.org/v1/species/search?q=Panthera leo&limit=10`

### 3. Get Occurrence by ID

- **Endpoint**: `GET https://api.gbif.org/v1/occurrence/{{occurrenceId}}`

---

## iNaturalist - Wildlife Observations

iNaturalist API for wildlife observations and species identification. Read operations are public.

### 1. Get Observations

- **Endpoint**: `GET https://api.inaturalist.org/v1/observations?taxon_name=Panthera leo&per_page=10`

### 2. Get Species Identifications

- **Endpoint**: `GET https://api.inaturalist.org/v1/identifications?taxon_id=12345&per_page=10`

### 3. Get Observation Details

- **Endpoint**: `GET https://api.inaturalist.org/v1/observations/{{observationId}}`

---

## Movebank - Animal Tracking

Requires **Basic Auth** (`{{movebank_username}}` / `{{movebank_password}}`).

### 1. Get Studies

- **Endpoint**: `GET https://www.movebank.org/movebank/service/direct-read?entity_type=study`

### 2. Get Animals in Study

- **Endpoint**: `GET https://www.movebank.org/movebank/service/direct-read?entity_type=individual&study_id={{study_id}}`

### 3. Get Animal Tracks

- **Endpoint**: `GET https://www.movebank.org/movebank/service/direct-read?entity_type=event&study_id={{study_id}}&individual_id={{individual_id}}`

---

## IUCN Red List - Conservation Status

Requires `{{iucn_api_token}}` as a query parameter.

### 1. Get Species by Name

- **Endpoint**: `GET https://apiv3.iucnredlist.org/api/v3/species/{{speciesName}}?token={{iucn_api_token}}`

### 2. Get Conservation Status

- **Endpoint**: `GET https://apiv3.iucnredlist.org/api/v3/species/history/name/{{speciesName}}?token={{iucn_api_token}}`

### 3. Get Threatened Species List

- **Endpoint**: `GET https://apiv3.iucnredlist.org/api/v3/species/page/{{page}}?token={{iucn_api_token}}`

---

## NASA Earthdata - Environmental Data

Requires NASA Earthdata credentials for some endpoints.

### 1. Search Environmental Datasets

- **Endpoint**: `GET https://cmr.earthdata.nasa.gov/search/collections.json?keyword=wildlife habitat&page_size=10`

### 2. Search Data Granules

- **Endpoint**: `GET https://cmr.earthdata.nasa.gov/search/granules.json?short_name=MOD13A1&page_size=10`

### 3. Get Climate Data

- **Endpoint**: `GET https://cmr.earthdata.nasa.gov/search/collections.json?keyword=climate temperature&page_size=10`

---

## Authentication Summary

| API | Auth Type | Variable(s) |
|---|---|---|
| GBIF | None | - |
| iNaturalist | None (read) | - |
| Movebank | Basic Auth | `{{movebank_username}}`, `{{movebank_password}}` |
| IUCN Red List | API Token | `{{iucn_api_token}}` |
| NASA Earthdata | Earthdata credentials | - |
