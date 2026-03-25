# Movebank - Animal Tracking

Movebank API for animal movement and tracking data.

**Authentication:** Requires Basic Auth (`{{movebank_username}}` / `{{movebank_password}}`).

## 1. Get Studies

- **Endpoint**: `GET https://www.movebank.org/movebank/service/direct-read`

**Example Request:**

```
GET https://www.movebank.org/movebank/service/direct-read?entity_type=study
```

## 2. Get Animals in Study

- **Endpoint**: `GET https://www.movebank.org/movebank/service/direct-read`

**Example Request:**

```
GET https://www.movebank.org/movebank/service/direct-read?entity_type=individual&study_id={{study_id}}
```

## 3. Get Animal Tracks

- **Endpoint**: `GET https://www.movebank.org/movebank/service/direct-read`

**Example Request:**

```
GET https://www.movebank.org/movebank/service/direct-read?entity_type=event&study_id={{study_id}}&individual_id={{individual_id}}
```
