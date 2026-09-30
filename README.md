# Automotive Timing Belt OEM & Part Number Cross-Reference Database

A structured reference database for **automotive timing belt OEM part numbers, aftermarket cross references, vehicle applications, belt specifications, and verification sources**.

This project is designed for automotive parts buyers, distributors, importers, wholesalers, aftermarket suppliers, manufacturers, researchers, and technical users who need to identify and verify timing belt part-number relationships.

The database connects:

**OEM Part Number → Aftermarket Reference → Vehicle / Engine Application → Belt Specification → Verification Evidence**

## Quick Answer

A timing belt OEM part number cross reference is a documented relationship between an original equipment reference and one or more replacement references from aftermarket manufacturers or parts catalogs.

A cross-reference should **not** automatically be interpreted as universal interchangeability.

Before selecting or sourcing a replacement timing belt, verify:

* OEM part number
* Vehicle and engine application
* Aftermarket cross-reference
* Tooth profile
* Tooth pitch
* Tooth count
* Belt width
* Belt length
* Construction
* Source and verification status

The purpose of this repository is to make those relationships easier to identify, review, and maintain.

## What This Database Contains

The database is organized into several information layers.

### OEM Part Number Data

Original equipment manufacturer references used as the primary identification point.

### Aftermarket Cross References

Documented references from manufacturers and aftermarket catalogs, including:

* Gates
* Dayco
* Continental
* Bando
* Other validated aftermarket references as the database expands

### Vehicle Application Data

Where reliable information is available, records can include:

* Vehicle make
* Vehicle model
* Engine
* Model year
* Application notes

### Technical Specification Data

Where supported by reliable sources, records may include:

* Tooth profile
* Tooth pitch
* Tooth count
* Width
* Effective or pitch length
* Construction
* Other relevant belt characteristics

### Verification Data

Each record is intended to preserve evidence and distinguish different types of relationships.

Examples include:

* `OEM_VERIFIED`
* `APPLICATION_VERIFIED`
* `SPEC_VERIFIED`
* `CROSS_REFERENCE_VERIFIED`

## Important: Cross Reference Does Not Mean Universal Interchangeability

A part-number cross reference identifies a documented relationship between references.

It does not automatically prove that two belts are suitable for every vehicle, engine, or application.

Timing belt suitability depends on the complete application and technical specification.

For this reason, the database distinguishes:

### OEM Supersession

An OEM manufacturer replaces or supersedes an earlier OEM part number.

### Aftermarket Cross Reference

A source explicitly associates an OEM reference with an aftermarket part number.

### Application Reference

A part number is documented for a specific vehicle or engine application.

### Specification Verification

Technical belt characteristics are supported by a reliable specification source.

These relationships should not be treated as identical.

## Current Brand Index

The database will be expanded by vehicle and OEM brand while maintaining the same verification structure.

### Toyota

* [Toyota Timing Belt OEM Part Number Cross Reference](docs/toyota-timing-belt-cross-reference.md)
* [Toyota Timing Belt Cross-Reference Data](data/toyota.csv)
* [Toyota Timing Belt Application Data](data/toyota-applications.csv)

### Honda

Coming soon.

### Nissan

Coming soon.

### Mitsubishi

Coming soon.

### Mazda

Coming soon.

### Subaru

Coming soon.

### Hyundai / Kia

Coming soon.

### Lexus

Coming soon.

## Toyota Timing Belt Cross Reference

The Toyota section is the first expanded brand dataset in this repository.

It brings together Toyota OEM timing belt references with documented aftermarket references, application information, specifications, and source records.

See:

* [Toyota Timing Belt OEM Part Number Cross Reference](docs/toyota-timing-belt-cross-reference.md)
* [Toyota CSV Data](data/toyota.csv)
* [Toyota Application Data](data/toyota-applications.csv)
* [Toyota Source Records](sources/toyota-sources.md)

The Toyota dataset includes multiple timing belt reference families covering different OEM and aftermarket part-number relationships.

## Example Cross-Reference Relationships

The following examples illustrate how the data is organized.

### Toyota 13568-09041

```text
OEM:
Toyota 13568-09041

Aftermarket references:
Gates T199 / T199RB
Dayco 95199 / 95199FN
Continental 40199 / TB199
Bando TB199
```

### Toyota 13568-69075

```text
OEM:
Toyota 13568-69075

OEM previous version:
13568-65020

Aftermarket references:
Gates T240
Dayco 95240
```

### Toyota 13568-69095

```text
OEM:
Toyota 13568-69095

Aftermarket references:
Gates T271
Dayco 95271 / 95271FN
Continental 40271 / TB271
Bando TB271
```

These examples are provided to illustrate the database structure. Users should review the associated application and source records before treating a relationship as suitable for a specific vehicle or engine.

## Data Structure

The main dataset uses fields such as:

```text
cross_reference_group
oem_brand
oem_part_number
oem_supersession
gates_part_number
dayco_part_number
continental_part_number
bando_part_number
vehicle_make
vehicle_model
engine
year_from
year_to
teeth
tooth_pitch_mm
width_mm
effective_length_mm
tooth_profile
construction
relationship_type
verification_status
source_oem
source_cross_reference
source_specification
last_verified
notes
```

The repository also separates application data from the main cross-reference dataset to make future expansion easier.

## Verification Methodology

The database uses a structured verification approach rather than treating every part-number relationship as equally certain.

### OEM Verified

The OEM reference is supported by an OEM or authoritative manufacturer source.

### Application Verified

The vehicle, engine, or application information is supported by application data.

### Specification Verified

The technical belt specification is supported by a reliable technical or manufacturer source.

### Cross-Reference Verified

A reliable source explicitly documents the relationship between the OEM and aftermarket reference.

For more information, see the [Verification Methodology](VERIFICATION-METHODOLOGY.md).

Toyota-specific source and verification notes are available in:

* [Toyota Sources](sources/toyota-sources.md)
* [Verification Notes](sources/VERIFICATION-NOTES.md)

## Source Policy

This project aims to preserve source provenance for important data.

Sources may include:

* OEM manufacturer catalogs and parts databases
* Belt manufacturer catalogs
* Official manufacturer technical documentation
* Established aftermarket parts catalogs
* Reliable application databases
* Independent cross-reference sources

Where evidence is incomplete, the relevant field should remain blank rather than being filled through assumption.

The project distinguishes between factual reference data and inferred compatibility.

## Why Source Provenance Matters

Automotive part-number information can change over time.

OEM numbers may be superseded.

Aftermarket references may be revised or discontinued.

Application catalogs may be updated.

For this reason, records should retain:

```text
Source
Verification Status
Last Verified Date
Notes
```

This makes the database easier to audit, update, and maintain over time.

## Database Use

This database can be used for:

* OEM part-number identification
* Aftermarket replacement research
* Distributor product-range development
* Importer sourcing research
* Automotive parts catalog research
* Vehicle application verification
* Timing belt specification comparison
* Technical reference work

The database is intended to support research and identification.

Final product selection should always be confirmed against the appropriate manufacturer documentation and application requirements.

## Timing Belt Identification

This repository focuses on **cross-reference and verification** rather than explaining every aspect of timing belt coding.

For information about timing belt markings and how timing belt numbers are structured, see:

[Timing Belt Number Meaning: How to Read Belt Codes](https://chinarealshow.com/timing-belt-number-meaning/)

For a broader explanation of timing belt types, sizes, materials, identification, and selection, see:

[REALSHOW Timing Belt Guide](https://chinarealshow.com/timingbelt-guide/)

## Timing Belt vs Other Automotive Belt Categories

Automotive belts should be identified according to their actual function and design.

A **Timing Belt** is a toothed synchronous belt used for engine timing applications.

A **PK Belt**, commonly called a **Poly V-Belt**, uses longitudinal ribs and is generally associated with accessory-drive systems.

A **V-Belt** uses a V-shaped cross-section and corresponding pulley geometry.

A **Serpentine Belt** is a multi-ribbed accessory-drive belt designed to operate through a serpentine routing system.

These categories use different identification and specification principles and should not be cross-referenced as if they were the same belt type.

For a broader automotive belt overview, see the [REALSHOW Automotive Belt Guide](https://chinarealshow.com/automotive-belt-guide/).

## Related REALSHOW Resources

For detailed technical and sourcing information:

* [Timing Belt OEM Part Number Cross Reference Guide for Buyers](https://chinarealshow.com/timing-belt-oem-part-number-cross-reference/)
* [Timing Belt Guide](https://chinarealshow.com/timingbelt-guide/)
* [Automotive Timing Belt Manufacturing](https://chinarealshow.com/automotive-timing-belt-manufacturing/)
* [OEM Automotive Belt Manufacturer](https://chinarealshow.com/oem-automotive-belt-manufacturer/)
* [Automotive Belt Supplier Checklist](https://chinarealshow.com/automotive-belt-supplier-checklist/)

## About REALSHOW BELT

REALSHOW BELT is an automotive and industrial belt manufacturer and exporter established in 2000.

The product range includes:

* Timing Belts
* PK Belts
* Poly V-Belts
* Automotive V-Belts
* Agricultural Belts
* Motorcycle and Scooter Belts
* Industrial Belts

REALSHOW supports distributors, wholesalers, importers, aftermarket suppliers, and OEM customers in international markets.

For OEM automotive belt development and customized manufacturing, see:

[OEM Automotive Belt Manufacturer](https://chinarealshow.com/oem-automotive-belt-manufacturer/)

## Update Policy

This database is intended to expand progressively by vehicle and OEM brand.

New records should be added only when the relevant relationship can be supported by reliable evidence.

Future updates may include:

* Additional Toyota references
* Honda
* Nissan
* Mitsubishi
* Mazda
* Subaru
* Hyundai
* Kia
* Lexus
* Infiniti
* European vehicle manufacturers
* Additional aftermarket belt manufacturers

The objective is to build a structured and maintainable automotive timing belt reference database rather than a static list of unverified part numbers.

## Disclaimer

This repository is provided for research, identification, and reference purposes.

A cross-reference listing does not by itself guarantee universal interchangeability.

Always verify the specific vehicle, engine, application, belt profile, pitch, tooth count, width, length, and manufacturer documentation before ordering, installing, manufacturing, or distributing a timing belt.

OEM names, trademarks, and part numbers belong to their respective owners.

## Repository Structure

```text
timing-belt-oem-cross-reference/
│
├── README.md
├── VERIFICATION-METHODOLOGY.md
│
├── data/
│   ├── timing-belt-cross-reference.csv
│   ├── timing-belt-applications.csv
│   ├── toyota.csv
│   └── toyota-applications.csv
│
├── docs/
│   └── toyota-timing-belt-cross-reference.md
│
└── sources/
    ├── toyota-sources.md
    └── VERIFICATION-NOTES.md
```

## Related Guide

For a detailed explanation of how OEM timing belt numbers are cross-referenced, verified, and used for aftermarket and B2B sourcing, read the:

[Timing Belt OEM Part Number Cross Reference Guide for Buyers](https://chinarealshow.com/timing-belt-oem-part-number-cross-reference/)
