# ᛏ IUCN Red List - Conservation Status

> ᛏ **Tiwaz** — *justice & protection*: reflects the legal and ethical protection of threatened species.

IUCN Red List API for species conservation status and threatened species data.

**Authentication:** Requires `{{iucn_api_token}}` as a query parameter.

## ᛏ 1. Get Species by Name

- **Endpoint**: `GET https://apiv3.iucnredlist.org/api/v3/species/{{speciesName}}`

**Example Request:**

```
GET https://apiv3.iucnredlist.org/api/v3/species/{{speciesName}}?token={{iucn_api_token}}
```

## ᛏ 2. Get Conservation Status

- **Endpoint**: `GET https://apiv3.iucnredlist.org/api/v3/species/history/name/{{speciesName}}`
- **Description**: Retrieve the conservation assessment history for a species.

**Example Request:**

```
GET https://apiv3.iucnredlist.org/api/v3/species/history/name/{{speciesName}}?token={{iucn_api_token}}
```

## ᛏ 3. Get Threatened Species List

- **Endpoint**: `GET https://apiv3.iucnredlist.org/api/v3/species/page/{{page}}`
- **Description**: Retrieve a paginated list of threatened species.

**Example Request:**

```
GET https://apiv3.iucnredlist.org/api/v3/species/page/{{page}}?token={{iucn_api_token}}
```
