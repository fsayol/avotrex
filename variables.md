---
layout: default
title: Data dictionary
permalink: /variables/
---

[← Back to home]({{ '/' | relative_url }})

## Data dictionary (v{{ site.latest_version }})

The full definitions, including the raw data files, reference IDs, museum collections and measurers, are in [`Avotrex_metadata.xlsx`]({{ '/data/v1.0/Avotrex_metadata.xlsx' | relative_url }}). This page summarises the two main files. Taxonomy follows IUCN/BirdLife. External measurements follow AVONET (Tobias et al. 2022).

### Files in each release

| File | Content |
|---|---|
| `Avotrex_taxonomy` | One row per species: identifier, taxonomy, status, authority and common name |
| `Avotrex_traits` | One row per species: status, distribution, flight ability and external morphology (measured or imputed) |
| `RawData_D1` | External measurements of extinct species from museum skins |
| `RawData_D2` | External measurements of extinct species from the literature |
| `RawData_D3` | Skeletal measurements of extinct species from museum specimens |
| `RawData_D4` | Skeletal measurements of extinct species from the literature |
| `RawData_D5` | Body mass of extinct species from the literature |
| `RawData_D6` | Body mass of extinct species inferred from descriptions or skeletal proportions |
| `RawData_D7` | Skeletal measurements of extant species from museum specimens |
| `RawData_D8` | Skeletal measurements of extant species from the literature |
| `Avotrex_metadata.xlsx` | Variable definitions, reference IDs, collection IDs and measurer IDs |

### `Avotrex_taxonomy`

| Variable | Description |
|---|---|
| `sp_id` | Unique AVOTREX species identifier ("x" followed by a number). Stays the same across versions, even if the name changes. |
| `species` | Species name. Undescribed species use the tentative genus, "sp" and the location or an adjective (e.g. `Bubo_sp_Eivissa`). |
| `superorder`, `order`, `family`, `genus` | Higher taxonomy |
| `status` | Extinction status (see codes below) |
| `taxonomic_authority` | Author(s) and year of the first description |
| `formally_described` | Whether the species has been formally described (`yes`/`no`) |
| `common_name` | English common name |
| `authority_ref_id` | Reference ID of the taxonomic authority (full references in the metadata file) |

**Status codes**

| Code | Meaning |
|---|---|
| `EX` | Extinct after 1500 CE and recognised by the IUCN |
| `EH` | Undescribed or recently described species extinct after 1500 CE, not on the IUCN Red List |
| `EP` | Extinct between 130,000 years ago and 1500 CE, believed to be at least partly due to human actions |
| `EPU` | Same period as `EP`, but possibly extinct from natural causes unrelated to humans |
| `EW` | Extinct in the Wild |
| `CR` | Critically Endangered (Possibly Extinct) |

### `Avotrex_traits`

| Variable | Description | Units |
|---|---|---|
| `species`, `status`, `order`, `family` | As in the taxonomy file | |
| `island_endemicity` | `insular` if exclusively found on an island or island group not connected to a continent during the Last Glacial Maximum; otherwise `continental` | |
| `region` | Biogeographic region the species inhabited | |
| `archipelago` | Archipelago the species was endemic to (continental region for continental species) | |
| `lat`, `long` | Approximate centroid of the species' distribution, at archipelago or continent level | decimal degrees |
| `flight_ability` | `0` flightless; `0.5` weak flyer (flies only a few metres; flight is not its main way of moving); `1` fully volant | |
| `flight_imputation_type` | Whether flight ability comes from the literature (`Literature`) or was imputed (`Imputed`) | |
| `skin_imputation_type` | `Measured_skin` (from museum skins), `Imputed_from_skeleton` (imputed using skeletal measures) or `Imputed_from_bodySize` (imputed using body size) | |
| `beak_length_culmen` | Tip of the beak to the base of the skull | mm |
| `beak_length_nares` | Anterior edge of the nostrils to the tip of the beak | mm |
| `beak_width` | Beak width at the anterior edge of the nostrils | mm |
| `beak_depth` | Beak depth at the anterior edge of the nostrils | mm |
| `tarsus_length` | Posterior notch between tibia and tarsus to the last scale of the acrotarsium | mm |
| `wing_length` | Carpal joint to the tip of the longest primary, unflattened wing | mm |
| `kipps_distance` | Tip of the first secondary to the tip of the longest primary | mm |
| `tail_length` | Tip of the longest rectrix to where the two central rectrices protrude from the skin | mm |
| `body_mass` | Species average body mass (males and females) | g |
| `body_imputation_type` | `Literature`; `Estimated_from_descriptions` (qualitative descriptions or skeletal proportions); `Estimated_from_GenusMedian` / `Estimated_from_FamilyMedian` (median of congeneric / confamilial species); `Imputed` | |
| `n_emm` | Number of external measurements (out of 8) with data before imputation | count |
| `n_skel` | Number of skeletal measurements (out of 22 in v1.0) with data | count |
| `n_body` | Whether body mass data are available (`1` yes, `0` no) | |
