# Data Dictionary

## File formats

- **GeoJSON** (`startup-cultural-dataset_v1.0.0.geojson`): RFC 7946 FeatureCollection. Coordinates in `[longitude, latitude]` order (WGS84 / EPSG:4326). Features with unknown location have `"geometry": null`.
- **CSV** (`startup-cultural-dataset_v1.0.0.csv`): UTF-8 with BOM, comma-delimited, double-quote escaping. Latitude and longitude in separate decimal columns.

## Fields

| Field | Type | GeoJSON | CSV | Required | Description |
|-------|------|---------|-----|----------|-------------|
| `name` | string | properties | column | yes | Name of the venue or cultural place |
| `category` | string | properties | column | yes | Normalized category in snake_case. See category list below |
| `city` | string | properties | column | yes | City or metropolitan area. Values: `Stockholm`, `Madrid`, `Rome`, `Gdańsk`, `Sevilla`, `Trenčín`, `Eurométropole de Strasbourg`, `Dortmund Bochum Gelsenkirchen` |
| `latitude` | float | geometry.coordinates[1] | column | no | WGS84 latitude. Empty/null if coordinates unknown |
| `longitude` | float | geometry.coordinates[0] | column | no | WGS84 longitude. Empty/null if coordinates unknown |
| `website` | string | properties | column | no | URL of the venue. Normalized with `https://` prefix where missing |
| `comments` | string | properties | column | no | Free-text notes |
| `source` | string | properties | column | no | `user_submitted` if manually added by project partners; empty if derived from Overture Maps |
| `color` | string | properties | — | no | Hex color code for map rendering (GeoJSON only, not in CSV) |
| `category2` | string | properties | — | no | Secondary display category for user-submitted places (GeoJSON only) |
| `note` | string | properties | — | no | System note, e.g. `No coordinates` (GeoJSON only) |

## Category vocabulary

Categories are normalized to snake_case. The full list includes ~70 types. Main groupings:

**Museums:** `art_museum`, `contemporary_art_museum`, `modern_art_museum`, `museum`, `history_museum`, `science_museum`, `national_museum`, etc.

**Galleries:** `art_gallery`

**Performance:** `theatre`, `opera_and_ballet`, `cinema`, `music_venue`, `dance_club`, `cabaret`, `circus`

**Community:** `cultural_center`, `community_center`, `community_services_non_profits`, `library`, `social_club`

**Education:** `art_school`, `drama_school`, `music_school`, `dance_school`, `architecture_schools`

**Creative production:** `art_space_rental`, `atelier`, `recording_and_rehearsal_studio`, `video_film_production`, `graphic_designer`, `photographer`

**Retail:** `bookstore`, `craft_shop`, `art_supply_store`, `vinyl_record_store`

**Other:** `festival`, `street_art`, `urban_farm`, `community_gardens`, `makerspace`

**Project-specific:** Categories prefixed with `Startup` (e.g. `Startup Artist studios`) are additions by project partners not present in the Overture Maps taxonomy.

## Null values

- Empty strings (`""`) indicate no value.
- In GeoJSON, `"geometry": null` indicates unknown coordinates.
- In CSV, empty `latitude` and `longitude` fields indicate unknown coordinates.
