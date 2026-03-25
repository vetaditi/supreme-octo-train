# NASA Earthdata - Environmental Data

NASA Common Metadata Repository (CMR) API for environmental and climate datasets. Some endpoints require NASA Earthdata credentials.

## 1. Search Environmental Datasets

- **Endpoint**: `GET https://cmr.earthdata.nasa.gov/search/collections.json`

**Example Request:**

```
GET https://cmr.earthdata.nasa.gov/search/collections.json?keyword=wildlife habitat&page_size=10
```

## 2. Search Data Granules

- **Endpoint**: `GET https://cmr.earthdata.nasa.gov/search/granules.json`

**Example Request:**

```
GET https://cmr.earthdata.nasa.gov/search/granules.json?short_name=MOD13A1&page_size=10
```

## 3. Get Climate Data

- **Endpoint**: `GET https://cmr.earthdata.nasa.gov/search/collections.json`

**Example Request:**

```
GET https://cmr.earthdata.nasa.gov/search/collections.json?keyword=climate temperature&page_size=10
```
