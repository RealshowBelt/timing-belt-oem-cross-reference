# Verification Methodology

## Evidence hierarchy

Preferred evidence order:

1. OEM or OEM-parts source for OEM identity and supersession.
2. Original manufacturer catalog/product source for aftermarket part specifications and applications.
3. Established parts-distribution source for explicit cross-reference relationships.
4. Established application database for vehicle/model/year evidence.
5. Secondary interchange catalogs as supporting evidence when stronger sources are not available.

## Cross-reference rule

`CROSS_REFERENCE_VERIFIED` requires an explicit OEM-to-aftermarket or reverse aftermarket-to-OEM relationship in an inspectable source.

## Specification rule

Dimensions are recorded only when the specification source explicitly provides them. Same dimensions alone do not establish interchangeability.

## Application rule

Vehicle applications are stored separately from the master part-number relationship table because a single part number can cover different models and year ranges. Exact engine information is recorded only when explicitly supported.

## Supersession rule

OEM supersession is stored as a separate relationship concept from aftermarket interchange. A superseded OEM number does not automatically inherit all aftermarket relationships unless the evidence supports the relationship.

## Source provenance

Every production row should retain source URL(s), verification status, last-verified date, and a note for ambiguity or special restrictions.

## REALSHOW mapping rule

REALSHOW part numbers should be added only after the objective OEM/application relationship has been established. REALSHOW mapping must not be used as evidence to establish a competitor cross-reference.

## Update discipline

Before each release, recheck changed or disputed rows against current source pages/catalogs. If an evidence page disappears or changes materially, downgrade or remove the affected claim rather than preserving an unsupported statement.
