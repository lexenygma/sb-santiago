# Santiago de los Caballeros (STI) — Subway Builder Map

A playable map of Santiago de los Caballeros, Dominican Republic for [Subway Builder](https://www.subwaybuilder.com/), installable via [Railyard](https://subwaybuildermodded.com/railyard).

The heart of the Cibao Valley — build a metro for the Dominican Republic's second city, from the Monumento to the zona franca.

## Coverage

- **Bounding box:** 70.90–70.55°W, 19.35–19.58°N — Santiago municipality plus Tamboril, Villa González, Licey al Medio, and Cibao International Airport (STI)
- **Population:** ~923,000 residents across 2,447 demand points (~400 m resolution)
- **Airport:** Cibao International (STI/MDST) runways and taxiways included

## Data sources & methodology

| Layer | Source | Method |
|---|---|---|
| Base map tiles | OpenStreetMap via Protomaps Basemap | `pmtiles extract` from the Protomaps daily planet build |
| Population | [WorldPop](https://www.worldpop.org/) 2020 UN-adjusted constrained 100 m raster (DOM) | Aggregated to ~400 m blocks with population-weighted centroids |
| Jobs & commutes | Synthesized | Gravity model over 8 employment zones (Monumento/Centro, Av. J.P. Duarte corridor, Zona Franca Víctor Espaillat, PUCMM, UTESA, Cibao airport, Pueblo Nuevo, Gurabo); commuter groups assigned by distance-weighted allocation |
| Roads | OpenStreetMap | osmium extract, depot road classification (~17k features) |
| Buildings | [Overture Maps](https://overturemaps.org/) 2026-06 (~259k footprints after cleanup) | mapshaper cleanup per depot recipe; game JSON + binary index formats |
| Runways/taxiways | OpenStreetMap | depot aeroway processing |

Residents are modeled gridded population (WorldPop, census-constrained); the bbox total (~924k) closely matches the 2022 census for the metro area. Jobs are **not** from an official commuting matrix — employment distribution is modeled.

## Compatibility

Ships both `buildings_index.json` (game ≤ 1.3) and `buildings_index.bin` (game ≥ 1.4).

## Attribution & license

- Map data © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors, ODbL.
- Building footprints © [Overture Maps Foundation](https://overturemaps.org/), ODbL/CDLA-Permissive-2.0.
- Population: [WorldPop](https://www.worldpop.org/) (CC BY 4.0), University of Southampton.
- Map package: free to use with Subway Builder via Railyard.
