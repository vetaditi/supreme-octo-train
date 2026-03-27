# ᚠ GBIF - Biodiversity Data

> ᚠ **Fehu** — *wealth & abundance*: reflects the vast abundance of global species occurrence records.

Global Biodiversity Information Facility API for species occurrence and biodiversity data. No authentication required.

## ᚠ 1. Search Species Occurrences

- **Endpoint**: `GET https://api.gbif.org/v1/occurrence/search`
- **Description**: Search for species occurrence records by scientific name.

**Parameters:**

| Name | Type | Example Value | Description |
|---|---|---|---|
| scientificName | string | Panthera leo | Scientific name |
| limit | int | 10 | Results per request |

**Example Request:**

```
GET https://api.gbif.org/v1/occurrence/search?scientificName=Panthera leo&limit=10
```

## ᚠ 2. Get Species Info

- **Endpoint**: `GET https://api.gbif.org/v1/species/search`

**Example Request:**

```
GET https://api.gbif.org/v1/species/search?q=Panthera leo&limit=10
```

## ᚠ 3. Get Occurrence by ID

- **Endpoint**: `GET https://api.gbif.org/v1/occurrence/{{occurrenceId}}`
- **Description**: Retrieve a specific occurrence record by its unique identifier.
