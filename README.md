# Garage Smart Farm V1

**A six-month systems-engineering experiment spanning physical design, hydroponics, edge computer vision, structured operational data, and commercial validation.**

From March through September 2026, I designed, fabricated, instrumented, operated, and analyzed a garage-scale growing system to answer a practical question:

> Could an unused one-car garage become a low-touch production system capable of generating meaningful income?

The answer was mixed in the useful way. The physical platform worked. The original commodity-basil business thesis did not close at the measured production rate.

That made the project valuable as an engineering case study: it moved from hypothesis -> build -> commissioning -> operation -> measurement -> failure analysis -> commercial decision.

## System

The physical pilot used:

- 4 NFT channels
- 19 nominal sites per channel
- **76 nominal growing sites**
- recirculating reservoir and continuous pump operation
- production lighting and circulation airflow
- propagation / Root Spa area
- six basil cultivars
- fixed-camera imaging
- Raspberry Pi edge compute
- Python + OpenCV canopy analysis
- structured plant, site, event, harvest, and forecast records

The intended fully populated rack geometry was **10 channels / 190 nominal sites**. Older 152-site planning models were superseded during final review.

## Software architecture

The camera pipeline evolved into:

```text
Capture -> Align -> Crop -> Mask -> Metrics -> Persist -> Dashboard
                                      |
                                      +-> structured farm state / harvest history
```

One of the strongest technical lessons was architectural:

**Structured site ledger = canonical farm state.**  
**Computer vision = measurement / trend sensor.**

Vision was useful for canopy trends, harvest impact, recovery, visual inspection, and evidence. It was not reliable enough to own exact occupancy, cultivar identity, or per-plant biomass.

## Six months in numbers

| Metric | Result |
| --- | ---: |
| Physical pilot | 76 nominal NFT sites |
| Full-rack geometry | 190 nominal sites |
| Cultivars | 6 |
| Harvest records | 24 |
| Repo-recorded biomass | 3,472 g |
| Reviewed intentional production | 3,346 g |
| Strict measured production | 3,304 g |
| Valid analyzed camera snapshots | 45 |
| Environmental readings | 99,866 |
| Farm events | 61 |
| Mature Genovese rate | 0.568 g/productive-site/day |
| Routine mature operation | ~10 min/day + reservoir service + harvests |

The mature Genovese run-rate uses the repeated Jul 22-Sep 7 interval following the Jul 11 cohort anchor: **1,681 g over 58 days across approximately 51 productive sites**.

That is approximately:

- 29.0 g/day across the cohort
- 3.98 g/site/week
- 207 g/site/year annualized

The early planning assumption had been roughly 20 g/site/week. Real operation replaced that assumption with measured evidence.

## What worked

- Repeated harvests continued through summer.
- Genovese basil did not bolt despite garage temperatures reaching roughly 99 F.
- The system could be left unattended for multi-day trips.
- Mature routine operation required little daily attention.
- Specialty cultivars produced useful product-learning beyond commodity Genovese.
- The system generated enough evidence to make a defensible commercial decision.

## What broke

The most important late-season failure was mechanical / hydraulic rather than biological.

Root biomass formed a dense mat across the channel bottoms, restricted drainage, increased standing water at the low end, and eventually exposed imperfect upper channel seams.

The plants had grown well enough to create a hydraulic constraint.

That changed the next design priorities toward:

- root and drain management
- channel sealing
- service access
- deliberate lighting design
- canopy utilization
- measured nutrient control
- crop spacing and cultivar selection

## Commercial conclusion

The original livelihood hypothesis did not close for commodity basil.

At the measured mature Genovese rate, a six-rack garage scenario extrapolates to roughly:

- 1,140 nominal sites
- ~4.5 kg/week
- ~10 lb/week
- ~236 kg/year

That is a scenario extrapolation, **not observed garage-scale production**.

At ordinary restaurant / commodity basil pricing, the available footprint did not support the target **$3,000/month owner-income** goal.

The useful result was therefore a negative commercial conclusion backed by a working physical system and real production data.

The next hypothesis is different: whether a standardized managed growing system creates more customer value when installed **where food is consumed**, especially with specialty crops. That remains a future test, not a validated business.

## Data integrity

This public archive distinguishes:

- **Observed** - measurements and timestamped operating records
- **Reviewed** - operator-confirmed corrections or clarified semantics layered on frozen source history
- **Derived** - calculations such as g/site/day and annualized yield
- **Scenario** - scale-up, pricing, labor, and future commercial assumptions

The private development repository remains private because it contains machine-specific paths, local network information, backups, intermediate artifacts, and development history. This repository is a curated public archive rather than a mirror of the working repo.

## Repository map

```text
docs/       final case-study PDFs
data/       reviewed and sanitized public data extracts
analysis/   reviewed commercial-feasibility workbook
figures/    selected figures
images/     selected project photographs
```

## Files currently published

- [Reviewed harvest dataset](data/harvests_reviewed.csv)
- [Selected farm-event timeline](data/farm_events_selected.csv)
- [Final structured site map](data/final_site_map.csv)
- [Environmental daily summary](data/environment_daily.csv)
- [Data dictionary](data/DATA_DICTIONARY.md)

The binary case studies, workbook, figures, and photo set come from the frozen final project bundle and are intentionally kept separate from the private development repository.

## Portfolio

A shorter version of the story is being packaged at:

**https://trehumphries.com/work/garage-smart-farm**

The farm is not the point by itself. The project is evidence of taking an ambiguous physical problem through concept, build, commissioning, software integration, operation, measurement, failure analysis, and a commercial decision.
