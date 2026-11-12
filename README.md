# STARTUP Cultural Places Dataset

Art and cultural places in European cities, curated for the STARTUP project (Horizon Europe).

## Description

This dataset maps art and cultural venues across eight European cities/regions. It combines data from the Overture Maps Foundation *places* theme (release 2025-05-21.0) with locally curated submissions, filtered by official municipal boundaries from Eurostat GISCO LAU 2024 and Etalab EPCI.

**Cities covered:** Dortmund/Bochum/Gelsenkirchen (Ruhr area), Madrid, Stockholm, Rome, Gdansk, Sevilla, Trencin, Eurometropole de Strasbourg.

**Total records:** ~2100 cultural places (v1.0.0).

## Files

| File | Format | Description |
|------|--------|-------------|
| `startup-cultural-dataset_v1.0.0.geojson` | GeoJSON (RFC 7946) | Primary dataset with point geometries (WGS84 / EPSG:4326) |
| `startup-cultural-dataset_v1.0.0.csv` | CSV (UTF-8, BOM) | Flat tabular version with latitude/longitude columns |
| `DATA_DICTIONARY.md` | Markdown | Field definitions, types, and allowed values |
| `CHANGELOG.md` | Markdown | Version history |
| `LICENSE` | Text | CC BY 4.0 legalcode |

## Data dictionary (summary)

| Field | Type | Description |
|-------|------|-------------|
| `name` | string | Name of the venue |
| `category` | string | Normalized category (snake_case), e.g. `art_gallery`, `theatre`, `cultural_center` |
| `city` | string | City or metropolitan area name |
| `latitude` | float | WGS84 latitude (CSV only) |
| `longitude` | float | WGS84 longitude (CSV only) |
| `website` | string | URL, normalized with `https://` prefix |
| `comments` | string | Optional free-text notes |
| `source` | string | `user_submitted` if added manually; empty if from Overture |

See `DATA_DICTIONARY.md` for full details.

## Coordinate reference system

All coordinates are in **WGS84 (EPSG:4326)**. In the GeoJSON file, geometry follows the `[longitude, latitude]` convention per RFC 7946. In the CSV, separate `latitude` and `longitude` columns are provided.

## Coverage and known limitations

- 17 records lack coordinates (digital-only presences); these have `null` geometry in GeoJSON and empty lat/lon in CSV.
- Category normalization maps ~70 fine-grained types to a controlled vocabulary. Categories prefixed with `Startup` are project-specific additions not in the Overture taxonomy.
- The Ruhr area aggregates three municipalities into one unit; Eurometropole de Strasbourg is an EPCI comprising multiple communes.

## Provenance

- **Boundary data:** Eurostat GISCO LAU 2024 (1:1M, EPSG:4326); Etalab EPCI (SIREN 246700488)
- **Places data:** Overture Maps Foundation, places theme, release 2025-05-21.0 (CDLA Permissive 2.0)
- **Processing code:** [startup-cultural-data](https://github.com/horizon-startup-eu/startup-cultural-data) (Apache 2.0)
- **Extraction date:** 2026-08-31
- **Processing pipeline version:** commit `ba78758` of startup-cultural-data

## How to cite

> Borén, T., & Liistamo, M. (2026). *STARTUP Cultural Places Dataset* (v1.0.0) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.XXXXXXX

Replace the DOI placeholder with the actual DOI after publication.

## License

This dataset is licensed under the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).

Third-party data attributions:
- Overture Maps Foundation — Places (CDLA Permissive 2.0)
- Eurostat GISCO — LAU 2024 (reuse policy: free reuse with attribution)
- Etalab — EPCI (Licence Ouverte 2.0)
- OpenStreetMap contributors (ODbL) — basemap tiles only, not included in dataset

## EU funding acknowledgement

This project has received funding from the **European Union's Horizon Europe** research and innovation programme under **Grant Agreement No 101178523** (STARTUP — Sustainable Transitions: Action Research and Training in Urban Perspective).

Views and opinions expressed are those of the author(s) only and do not necessarily reflect those of the European Union or the granting authority. Neither the European Union nor the granting authority can be held responsible for them.

## Contact

Thomas Borén — Thomas.Boren@humangeo.su.se
Magnus Liistamo — magnus.liistamo@humangeo.su.se
Department of Human Geography, Stockholm University
