# Centers Density Analysis

Analysis of activity units per acre (jobs + households) vs. floor-area-ratio
(FAR) for regional growth centers.

The main notebook, [au_acre_far_existing.ipynb](au_acre_far_existing.ipynb), is
a [Quarto dashboard](https://quarto.org/docs/dashboards/). Cached input tables
live in `output/pipeline/*.parquet`; set `FORCE_MYSQL_REFRESH = True` in the
first cell to re-download them from MySQL.

## Rendering the dashboard locally

Requires the [Quarto CLI](https://quarto.org/docs/get-started/) in addition to
the Python dependencies:

```
uv sync
uv run quarto render au_acre_far_existing.ipynb
```

This produces `index.html` (plus a supporting `au_acre_far_existing_files/`
folder) in the repo root.

## Publishing to GitHub Pages

The rendered `index.html` and `au_acre_far_existing_files/` are committed to
the repo. After rendering locally, commit and push those files to `main`; the
site is served directly from the repo via GitHub Pages ("Deploy from a
branch" source, `main` branch, `/ (root)` folder) under
**Settings > Pages**.

