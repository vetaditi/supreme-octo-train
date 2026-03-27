# ᚲ Authentication Summary

> ᚲ **Kenaz** — *torch & knowledge*: illuminates the keys and credentials needed to access each API.

| Rune | API | Auth Type | Variable(s) |
|---|---|---|---|
| ᚠ | GBIF | None | - |
| ᛉ | iNaturalist | None (read) | - |
| ᚱ | Movebank | Basic Auth | `{{movebank_username}}`, `{{movebank_password}}` |
| ᛏ | IUCN Red List | API Token | `{{iucn_api_token}}` |
| ᛊ | NASA Earthdata | Earthdata credentials | - |

## Setup Notes

### Movebank
Register at [movebank.org](https://www.movebank.org) and use your username/password with HTTP Basic Authentication.

### IUCN Red List
Request an API token at [apiv3.iucnredlist.org](https://apiv3.iucnredlist.org/api/v3/token). Pass the token as the `token` query parameter on every request.

### NASA Earthdata
Create an account at [urs.earthdata.nasa.gov](https://urs.earthdata.nasa.gov). Some collection search endpoints are public, but granule downloads require authentication.
