# ᛉ iNaturalist - Wildlife Observations

> ᛉ **Algiz** — *protection & wildlife*: reflects the guardianship of wild species through community observation.

iNaturalist API for wildlife observations and species identification. Read operations are public.

## ᛉ 1. Get Observations

- **Endpoint**: `GET https://api.inaturalist.org/v1/observations`

**Example Request:**

```
GET https://api.inaturalist.org/v1/observations?taxon_name=Panthera leo&per_page=10
```

## ᛉ 2. Get Species Identifications

- **Endpoint**: `GET https://api.inaturalist.org/v1/identifications`

**Example Request:**

```
GET https://api.inaturalist.org/v1/identifications?taxon_id=12345&per_page=10
```

## ᛉ 3. Get Observation Details

- **Endpoint**: `GET https://api.inaturalist.org/v1/observations/{{observationId}}`
- **Description**: Retrieve detailed information about a specific observation.
