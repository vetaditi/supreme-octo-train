# ᛊ NASA Earthdata - Environmental Data

> ᛊ **Sowilo** — *sun & vital force*: reflects solar observation and the life-giving environmental data from above.

NASA Common Metadata Repository (CMR) API for environmental and climate datasets. Some endpoints require NASA Earthdata credentials.

## ᛊ 1. Search Environmental Datasets

- **Endpoint**: `GET https://cmr.earthdata.nasa.gov/search/collections.json`

**Example Request:**

```
GET https://cmr.earthdata.nasa.gov/search/collections.json?keyword=wildlife habitat&page_size=10
```

## ᛊ 2. Search Data Granules

- **Endpoint**: `GET https://cmr.earthdata.nasa.gov/search/granules.json`

**Example Request:**

```
GET https://cmr.earthdata.nasa.gov/search/granules.json?short_name=MOD13A1&page_size=10
```

## ᛊ 3. Get Climate Data

- **Endpoint**: `GET https://cmr.earthdata.nasa.gov/search/collections.json`

**Example Request:**

```
GET https://cmr.earthdata.nasa.gov/search/collections.json?keyword=climate temperature&page_size=10
```
