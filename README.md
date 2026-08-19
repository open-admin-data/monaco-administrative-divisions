# Monaco Administrative Divisions / Monaco



## Overview

| Item | Details |
|------|---------|
| Section | 3 |
| Ward | 10 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-08-19 |
| Website | [openadmindata.org/mc](https://openadmindata.org/mc/) |
| API | [openadmindata.org/api/mc](https://openadmindata.org/api/mc/) |
| National Anthem | [🎵 Listen & Download Monaco National Anthem MP3](https://onlygames.me/national-anthems/mc/) |

## Browse by Section

| # | Section | Wards | Link |
|---|----|----|------|
| 1 | Monaco-Ville | 2 | [Browse](divisions/monaco-ville-mc01/) |
| 2 | Monte-Carlo (Monte Carlo) | 3 | [Browse](divisions/monte-carlo-mc02/) |
| 3 | La Condamine | 5 | [Browse](divisions/la-condamine-mc03/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-section.json](data/all-section.json) | JSON | All 3 section records |
| [all-ward.json](data/all-ward.json) | JSON | All 10 ward records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-1 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-section.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['ward']} wards")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-section.json", "utf-8"));
console.log(`Total: ${data.length} sections`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=section, 2=ward |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{section-slug}/
```

Wards are listed inline in each section's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-section links
- [Per-section data](docs/llms-full/) — Full data by section

## Citation

```
Monaco Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/monaco-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
