# Halal certification dashboard

A Streamlit dashboard exploring a **synthetic** halal-industry dataset with 250
application records and 24 attributes (business category, district, certification
status, application date, processing time, documentation completeness, fees, risk
level, and related fields).

> **Data notice:** every value is generated for demonstration purposes. These are
> **not official statistics** and must not be reported as such.

## Run the dashboard

From this folder:

```bash
python -m streamlit run streamlit_app.py
```

Then open the local URL shown in the terminal (usually `http://localhost:8501`).

The app reads `csv/halal_certification_synthetic_data.csv`. The generator in this
workspace is named `synthetic_data,py` (a comma instead of a dot); it was run from
inside the `csv` folder to create the CSV there.

## What the dashboard shows

| Requirement / concept | Where it appears |
| --- | --- |
| Category and district comparisons | **Comparisons** tab: ranked horizontal bars, category × district heatmap, ranked summary tables |
| Status composition | **Overview** tab: donut chart, status table, 100% stacked bars by category or district |
| Processing-time distributions | **Processing time** tab: histogram, boxplots by category or district, summary statistics |
| Temporal trends | **Overview** tab: monthly application volume with 3-month moving average, monthly average processing time |
| Relationship: volume vs processing time | **Processing time** tab: scatterplots by category and by month |
| Ranking | Ranked bar charts and numbered summary tables |
| Geospatial possibility | **Comparisons** tab: district-centroid bubble map with an explicit disclaimer |
| Dashboard interaction | Combined live clock and static day/month/year date label in the header, sidebar filters (date, category, district, status, size), select-all / clear-all quick actions, active-filter summary, segmented controls, tooltips, expandable tables, CSV download, reset button |

## Files

- `streamlit_app.py` — dashboard application
- `csv/halal_certification_synthetic_data.csv` — generated synthetic dataset
- `synthetic_data,py` — provided data generator
- `requirements.txt` — Python dependencies

## Notes

- Map coordinates are **approximate district centroids** used only to demonstrate a
  geospatial view. They are not official office locations or district boundaries.
- Filtering updates every chart, KPI and the downloadable CSV together.
- The dashboard handles empty filter results with a warning instead of an error.
