# ᚱ Movebank - Animal Tracking

> ᚱ **Raidho** — *journey & movement*: reflects the paths and migrations of tracked animals across the landscape.

Movebank API for animal movement and tracking data.

**Authentication:** Requires Basic Auth (`{{movebank_username}}` / `{{movebank_password}}`).

## ᚱ 1. Get Studies

- **Endpoint**: `GET https://www.movebank.org/movebank/service/direct-read`

**Example Request:**

```
GET https://www.movebank.org/movebank/service/direct-read?entity_type=study
```

## ᚱ 2. Get Animals in Study

- **Endpoint**: `GET https://www.movebank.org/movebank/service/direct-read`

**Example Request:**

```
GET https://www.movebank.org/movebank/service/direct-read?entity_type=individual&study_id={{study_id}}
```

## ᚱ 3. Get Animal Tracks

- **Endpoint**: `GET https://www.movebank.org/movebank/service/direct-read`

**Example Request:**

```
GET https://www.movebank.org/movebank/service/direct-read?entity_type=event&study_id={{study_id}}&individual_id={{individual_id}}
```
