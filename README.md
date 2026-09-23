# Automotive Timing Belt OEM & Part Number Cross Reference

A curated, source-backed database for automotive timing-belt OEM and aftermarket part-number relationships.

This repository is intended for parts identification, catalog normalization, application research, B2B sourcing, and long-tail searches involving OEM and aftermarket timing-belt numbers.

> **Important:** A cross-reference entry is not a universal interchangeability guarantee. Always verify the exact vehicle, engine, model year, OEM number, tooth count, pitch, width, tooth profile, and the current manufacturer application catalog before ordering or installing a timing belt.

## Release scope

This release is a **curated seed dataset**, not an exhaustive catalog. It contains 12 cross-reference groups covering Toyota, Honda, Nissan, and Mitsubishi relationships for which the available evidence supports the listed identifiers.

The repository separates:

- `data/timing-belt-cross-reference.csv` — normalized part-number and specification relationships.
- `data/timing-belt-applications.csv` — vehicle/application evidence kept separately from the master cross-reference table.
- `VERIFICATION-METHODOLOGY.md` — evidence rules and update discipline.

## Why applications are stored separately

A single aftermarket timing-belt number can fit multiple vehicles over different year ranges. Combining all those applications into one `year_from/year_to` field can create misleading ranges.

For example, Dayco 95184 covers Acura Integra (1990–2001) and Honda CR-V (1997–2001). The master cross-reference table therefore does not pretend that one 1990–2001 range applies to every vehicle in the group. Application evidence is stored row-by-row instead.

## Master data fields

The main CSV contains:

- `cross_reference_group`
- `oem_brand`
- `oem_part_number`
- `oem_related_numbers`
- `gates_part_number`
- `dayco_part_number`
- `continental_part_number`
- `bando_part_number`
- `teeth`
- `tooth_pitch_mm`
- `width_mm`
- `effective_length_mm`
- `tooth_profile`
- `construction`
- `relationship_type`
- `verification_status`
- `source_oem`
- `source_cross_reference`
- `source_specification`
- `last_verified`
- `notes`

## Verification status

`OEM_VERIFIED` — the OEM number is supported by an OEM or established OEM-parts source.

`APPLICATION_VERIFIED` — a source explicitly supports a vehicle/application relationship.

`SPEC_VERIFIED` — a source explicitly provides technical dimensions or construction data.

`CROSS_REFERENCE_VERIFIED` — a source explicitly connects an OEM number with an aftermarket part number, or a reputable source provides a reverse cross-reference that independently connects the identifiers.

A row may have evidence from more than one source type even though the current master status is summarized as `CROSS_REFERENCE_VERIFIED`.

## Critical distinction: OEM supersession vs aftermarket cross-reference

An OEM supersession is not automatically an aftermarket interchange.

If an OEM catalog says that part A was replaced by part B, that fact does not by itself prove that every Gates, Dayco, Continental, or Bando number associated with A or B is interchangeable in every application.

For that reason, this repository treats these as different concepts:

- `OEM_SUPERSESSION`
- `AFTERMARKET_CROSS_REFERENCE`
- `APPLICATION_REFERENCE`

## Data-quality rule

**No source → no claim.**

Unsupported engine codes, model years, dimensions, tooth profiles, materials, or competitor cross-references are left blank rather than inferred.

Identical dimensions are also not treated as proof of interchangeability. Application, tooth profile, OE specification, and manufacturer catalog evidence must be considered.

## Source policy

The repository organizes factual identifiers and application data from public OEM, manufacturer, catalog, and established parts sources. It does not reproduce complete proprietary catalogs.

Source URLs are retained so a future maintainer can re-check the evidence. Manufacturer names and part numbers remain identifiers of their respective manufacturers.

## REALSHOW manufacturer mapping

REALSHOW timing-belt references should be added only after the objective OEM/application relationship is established.

Recommended future fields:

`realshow_part_number`

`realshow_product_url`

`realshow_application_status`

`realshow_notes`

A REALSHOW number should be presented as manufacturer reference information, not as proof of interchangeability unless that relationship has separately been verified.

## REALSHOW timing-belt cluster

Recommended knowledge path:

**Part-number search → GitHub cross-reference database → REALSHOW Timing Belt Guide → Timing Belt category → product/application page → B2B sourcing**

Related REALSHOW pages:

- https://chinarealshow.com/timingbelt-guide/
- https://chinarealshow.com/product-category/automotive-belts/timing-belts-automotive-belts/
- https://chinarealshow.com/product/automotive-timing-belts-za-zbs-sp-ru-yu-s8m-mr-my/
- https://chinarealshow.com/automotive-belt-guide/
- https://chinarealshow.com/automotive-belt-manufacturer/

## Important source examples

Gates provides an automotive timing-belt product database with part numbers and specifications: https://www.gates.com/us/en/power-transmission/automotive-timing-belts/automotive-timing-belts.p.8595-000000-000000.html

Dayco publishes timing-belt catalogs and application material, including timing-belt dimensions and vehicle coverage: https://na.daycoaftermarket.com/wp-content/uploads/LD-HD-BLT-DIMGUIDE-1019_Auto-and-HD-Dim-and-ID-Guide.pdf

## Disclaimer

Cross-reference information is provided for research and identification purposes. Catalogs, applications, supersessions, and aftermarket coverage can change. Always confirm the current application with the relevant manufacturer or OEM documentation before purchasing or installing a timing belt.

**Last verified:** 2026-09-23
