# Authentication Summary

| API | Auth Type | Variable(s) |
|---|---|---|
| GBIF | None | - |
| iNaturalist | None (read) | - |
| Movebank | Basic Auth | `{{movebank_username}}`, `{{movebank_password}}` |
| IUCN Red List | API Token | `{{iucn_api_token}}` |
| NASA Earthdata | Earthdata credentials | - |

## Setup Notes

### Movebank
Register at [movebank.org](https://www.movebank.org) and use your username/password with HTTP Basic Authentication.

### IUCN Red List
Request an API token at [apiv3.iucnredlist.org](https://apiv3.iucnredlist.org/api/v3/token). Pass the token as the `token` query parameter on every request.

### NASA Earthdata
Create an account at [urs.earthdata.nasa.gov](https://urs.earthdata.nasa.gov). Some collection search endpoints are public, but granule downloads require authentication.
