# STARTUP Cultural Places Dataset

Art and cultural places in European cities, curated for the STARTUP project (Horizon Europe).

## Description

This dataset maps art and cultural venues across eight European cities/regions. It combines data from the Overture Maps Foundation *places* theme (release 2025-05-21.0) with locally curated submissions, filtered by official municipal boundaries from Eurostat GISCO LAU 2024 and Etalab EPCI.

**Cities:** Dortmund/Bochum/Gelsenkirchen (Ruhr), Madrid, Stockholm, Rome, Gdansk, Sevilla, Trencin, Eurometropole de Strasbourg.

**Records:** ~2100 cultural places. Coordinates in WGS84 (EPSG:4326).

## Fields

| Field | Description |
|-------|-------------|
| `name` | Name of the venue |
| `category` | Normalized category, e.g. `art_gallery`, `theatre`, `cultural_center` |
| `city` | City or metropolitan area |
| `website` | URL |
| `comments` | Optional notes |
| `source` | `user_submitted` if added manually; empty if from Overture |

Coordinates are stored in `geometry.coordinates` as `[longitude, latitude]` per GeoJSON spec. 17 records lack coordinates (`"geometry": null`).

## Provenance

- **Places:** Overture Maps Foundation, release 2025-05-21.0 (CDLA Permissive 2.0)
- **Boundaries:** Eurostat GISCO LAU 2024; Etalab EPCI (SIREN 246700488)
- **Processing code:** [startup-cultural-data](https://github.com/horizon-startup-eu/startup-cultural-data) (Apache 2.0)
- **Extraction date:** 2026-08-31

## How to cite

> Borén, T., & Liistamo, M. (2026). *STARTUP Cultural Places Dataset* (v1.0.0) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.XXXXXXX

## License

[Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/)

Third-party attributions: Overture Maps Foundation (CDLA Permissive 2.0), Eurostat GISCO (free reuse with attribution), Etalab (Licence Ouverte 2.0).

## EU funding acknowledgement

This project has received funding from the **European Union's Horizon Europe** research and innovation programme under **Grant Agreement No 101178523** (STARTUP — Sustainable Transitions: Action Research and Training in Urban Perspective).

Views and opinions expressed are those of the author(s) only and do not necessarily reflect those of the European Union or the granting authority. Neither the European Union nor the granting authority can be held responsible for them.

## Contact

Thomas Borén — Thomas.Boren@humangeo.su.se
Magnus Liistamo — magnus.liistamo@humangeo.su.se
Department of Human Geography, Stockholm University
