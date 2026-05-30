# Inactive oil & gas wells near drinking water protection zones in the Netherlands

Data investigation analysing the proximity of inactive oil and gas wells to drinking water protection zones in the Netherlands, using open government data.

## Research question

How many inactive oil and gas wells in the Netherlands are located within or near drinking water protection zones, and which operators are responsible for them?

## Data sources

- **NLOG borehole register**: [nlog.nl/datacenter/brh-overview](https://www.nlog.nl/datacenter/brh-overview) — public register of all oil and gas boreholes in the Netherlands.
- **PDOK grondwaterbeschermingsgebieden**: [PDOK Atom feed](https://service.pdok.nl/provincies/grondwaterbeschermingsgebieden/atom/am-gwbg.xml) — groundwater protection zones designated by Dutch provinces.

## Repository structure

```
├── netherlands-boreholes-analysis.ipynb   # Part 1: Data preparation and filtering
├── water-zones-boreholes.ipynb            # Part 2: Spatial analysis and visualisations
├── findings_report.docx                   # Summary document (2 pages)
├── data/
│   ├── nlog-boreholes-filtered.csv        # Filtered boreholes (output of Part 1)
│   ├── water_protection_zones.gml         # PDOK water protection zones (source)
│   └── water_zones_datawrapper.geojson    # Simplified zones for Datawrapper
├── boreholes_for_map_near.csv             # Wells near zones (for Datawrapper map)
├── chart_provinces.csv                    # Province summary (for Datawrapper chart)
├── chart_data.csv                         # Category summary (for Datawrapper chart)
└── *.png                                  # Datawrapper visualisations
```

## How to reproduce

### Requirements

- Python 3.8+
- Jupyter Notebook

### Setup

```bash
pip install pandas geopandas pyogrio openpyxl shapely matplotlib
```

### Steps

1. Download the NLOG borehole data from [NLOG Datacenter](https://www.nlog.nl/datacenter/brh-overview) and save as `data/2026-05-30-nlog-boreholes.xlsx`.
2. The water protection zones file (`data/water_protection_zones.gml`) is included in this repository.
3. Run **Part 1** (`netherlands-boreholes-analysis.ipynb`) — this filters and prepares the borehole data.
4. Run **Part 2** (`water-zones-boreholes.ipynb`) — this performs the spatial analysis against water protection zones.

### Note

The NLOG Excel file is not included in this repository due to size. Download it directly from the NLOG Datacenter link above.

## Visualisations

Visualisations were created with [Datawrapper](https://www.datawrapper.de/).

## AI disclosure

Claude Code (Anthropic) was used to assist with writing Python code for geospatial operations and data export.
