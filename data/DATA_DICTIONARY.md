# Public Data Dictionary

This directory is a reviewed public extract of the frozen Garage Smart Farm experiment archive.

## Provenance classes

- **Observed**: direct measurements or timestamped operating records.
- **Reviewed**: source values whose meaning was clarified by the operator during final review.
- **Derived**: calculations based on observed/reviewed values.
- **Scenario**: scale-up or commercial assumptions. These are not observed outcomes.

## harvests_reviewed.csv

One row per reviewed harvest/trim record.

- `repo_weight_g`: weight stored in the frozen experiment archive.
- `reviewed_total_g`: reviewed total used in the analysis layer. This differs only where contemporaneous notes justify a correction/clarification.
- `productive_sites`: productive-site denominator where supported.
- `reviewed_category`: intentional production, maintenance/trim, or estimated early prune.
- `strict_measured`: whether the mass is directly measured rather than partly estimated.
- `steady_state_genovese_cohort`: records belonging to the mature Genovese comparison cohort.
- `reviewed_g_per_site`: reviewed total divided by productive sites where applicable.

The mature Genovese production-rate calculation uses Jul 22-Sep 7 biomass (1,681 g) over 58 days following the Jul 11 cohort anchor, across approximately 51 productive sites.

## farm_events_selected.csv

Sanitized experiment timeline derived from the frozen event log. It intentionally omits internal IDs, machine paths, database paths, local-network information, and development-only metadata.

## final_site_map.csv

Structured rack site state from the final reviewed source ledger. The public extract keeps physical site identity, crop/cultivar, occupancy/status, planting date, and confidence/provenance fields only.

## environment_daily.csv

Daily aggregate temperature/humidity summary derived from the high-frequency logger record. The raw high-frequency environmental file is intentionally omitted from the public archive to keep the repository compact.

Logger coverage is discontinuous. Missing periods are preserved as missing data rather than interpolated.

## Important geometry

- Physical pilot: **4 channels × 19 sites = 76 nominal sites**
- Full rack: **10 channels × 19 sites = 190 nominal sites**

An older 8-channel / 152-site model existed during development and is superseded by the reviewed geometry.
