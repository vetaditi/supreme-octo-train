# Wildlife Health Monitoring API Documentation

A structured reference collection for integrating five public wildlife and
environmental monitoring APIs into One Health surveillance systems.

| | |
|---|---|
| **Author** | Dr. Aditi Sharma |
| **Affiliation** | Council for Environment and Sustainable Development (CESD), Dehradun, Uttarakhand, India |
| **Academic context** | MSc One Health
| **Professional context** | Wildlife Veterinarian; former Senior Veterinary Officer, Rajaji Tiger Reserve, Uttarakhand |
| **Year** | 2026 |
| **License** | Apache 2.0 — see [LICENSE](./LICENSE) |

---

## Purpose

Wildlife health surveillance requires integrating ecological and environmental
data alongside clinical and epidemiological reporting. This documentation
collection maps the five most relevant public APIs for that purpose —
covering species occurrence, animal movement, conservation status, community
observations, and environmental datasets.

It was developed as a reference layer for
[ZoonosesLink](https://github.com/vetaditi/zoonoseslink), an India zoonoses
cross-reporting system aligned with the National One Health Programme for
Prevention and Control of Zoonoses (NOHP-PCZ), NCDC/MoHFW, Government of India.

---

## APIs Covered

| API | Provider | Purpose | Auth |
|-----|----------|---------|------|
| [GBIF](./src/gbif.md) | Global Biodiversity Information Facility | Species occurrence and biodiversity records | None |
| [iNaturalist](./src/inaturalist.md) | iNaturalist / California Academy of Sciences | Community wildlife observations and species ID | None (read) |
| [Movebank](./src/movebank.md) | Max Planck Institute of Animal Behavior | Animal tracking and movement corridor data | Basic Auth |
| [IUCN Red List](./src/iucn.md) | International Union for Conservation of Nature | Conservation status and population trend | API Token |
| [NASA Earthdata](./src/nasa-earthdata.md) | NASA / EOSDIS | Land cover, NDVI, land surface temperature | Earthdata credentials |

**Coverage:** 15 endpoints across 5 APIs.

---

## One Health Relevance

Each API addresses a distinct surveillance gap at the human–wildlife–livestock
interface:

- **GBIF + iNaturalist** — establish presence/absence of reservoir and vector
  species near an outbreak location; support ecological plausibility assessment
- **Movebank** — identify movement corridors of key reservoir species (bats,
  NHPs, migratory birds); relevant for Nipah, KFD, avian influenza
- **IUCN Red List** — flag threatened species involvement in outbreak events,
  linking disease response to conservation obligations
- **NASA Earthdata** — characterise habitat type, vegetation index, and
  surface temperature at the outbreak site; supports vector activity modelling
  and land-use change analysis

---

## Repository Structure

```
supreme-octo-train/
│
├── wildlife-health-monitoring-api.md   ← Single-file flat reference (all 15 endpoints)
├── book.toml                           ← mdBook configuration
├── README.md                           ← This file
├── LICENSE                             ← Apache 2.0
│
└── src/
    ├── SUMMARY.md                      ← mdBook table of contents
    ├── introduction.md                 ← Overview and use cases
    ├── authentication.md               ← Credentials setup for all APIs
    ├── gbif.md                         ← GBIF endpoints (3)
    ├── inaturalist.md                  ← iNaturalist endpoints (3)
    ├── movebank.md                     ← Movebank endpoints (3)
    ├── iucn.md                         ← IUCN Red List endpoints (3)
    └── nasa-earthdata.md               ← NASA CMR endpoints (3)
```

---

## Building the mdBook Site

This documentation can be rendered as a static website using
[mdBook](https://rust-lang.github.io/mdBook/).

```bash
# Install mdBook (requires Rust)
cargo install mdbook

# Build static site
mdbook build

# Serve locally with live reload
mdbook serve
# Opens at http://localhost:3000
```

The built site can be deployed to GitHub Pages from the `gh-pages` branch or
the `/docs` folder.

---

## Authentication Quick Reference

| API | Method | Setup |
|-----|--------|-------|
| GBIF | None required | — |
| iNaturalist | None required (read) | — |
| Movebank | HTTP Basic Auth | Register at [movebank.org](https://www.movebank.org) |
| IUCN Red List | `?token=` query param | Request at [apiv3.iucnredlist.org/api/v3/token](https://apiv3.iucnredlist.org/api/v3/token) |
| NASA Earthdata | Earthdata credentials (granule download only) | Register at [urs.earthdata.nasa.gov](https://urs.earthdata.nasa.gov) |

---

## How to Cite This Work

If you use, adapt, or build on this documentation, the following citation is
required under the Apache 2.0 license attribution terms:

**Academic / report citation:**
> Sharma, A. (2026). *Wildlife Health Monitoring API Documentation: A reference
> collection for One Health surveillance systems.* Council for Environment and
> Sustainable Development, Dehradun, India.
> Available at: https://github.com/vetaditi/supreme-octo-train

**BibTeX:**
```bibtex
@misc{sharma2026wildlifeapi,
  author       = {Sharma, Aditi},
  title        = {Wildlife Health Monitoring API Documentation:
                  A reference collection for One Health surveillance systems},
  year         = {2026},
  institution  = {Council for Environment and Sustainable Development, Dehradun, India},
  url          = {https://github.com/vetaditi/supreme-octo-train},
  note         = {Licensed under Apache 2.0}
}
```

---

## Related Repository

**ZoonosesLink** — India Zoonoses Cross-Reporting API  
`https://github.com/vetaditi/zoonoseslink`

Integrates these five APIs as a background enrichment module to provide
ecological context for each zoonotic disease event reported through the
NOHP-PCZ surveillance chain (IDSP/IHIP ↔ NADRS/NDLM → SLZC/DLZC).

---

## License

Copyright © 2026 Dr. Aditi Sharma  
Council for Environment and Sustainable Development (CESD)  
Dehradun, Uttarakhand, India

Licensed under the **Apache License, Version 2.0**.
You may not use this work except in compliance with the License.
A copy of the License is included in this repository: [LICENSE](./LICENSE)
and is available at http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, content distributed
under this License is distributed on an **"AS IS" BASIS, WITHOUT WARRANTIES
OR CONDITIONS OF ANY KIND**, either express or implied.

> **Attribution is mandatory.** Any use, adaptation, or redistribution of this
> work must credit Dr. Aditi Sharma and the Council for Environment and
> Sustainable Development, Dehradun, as the originating author and institution.
