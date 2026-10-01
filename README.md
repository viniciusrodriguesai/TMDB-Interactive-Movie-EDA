# TMDB Interactive Movie EDA

A historical Jupyter project exploring a snapshot of popular TMDB movies with Python, pandas, Plotly and widgets. It combines API collection, genre analysis, financial summaries and a basic rating regression.

## Local setup

Create and activate a Python virtual environment, then run from the repository root:

```bash
python -m pip install -r requirements.txt
```

For live API collection, create a local `.env` containing your TMDB API Read Access Token:

```dotenv
TMDB_BEARER=replace_with_your_read_access_token
```

The notebook reads `TMDB_BEARER`, not `TMDB_API_KEY`. Never commit a real token. Start Jupyter **from the Notebooks directory**, since the notebook uses paths relative to that directory:

```bash
cd Notebooks
python -m jupyter lab TMDB_Interactive_EDA.ipynb
```

Run cells in order for the live workflow. Network access is required for API calls and connected Plotly rendering. Credentials and live widgets were not tested during the portfolio audit.

## Tracked data

- `Notebooks/data/raw/`: saved popular-movie API pages.
- `Notebooks/data/processed/movies_with_financials.csv`: 509 movies with financial fields.

The popular-movie snapshot is a selected sample. Its release-year distribution and financial totals do not estimate the entire film industry or establish pandemic effects.

## Verified corrections

CSV genre fields are safely decoded from list text before exploding: 509 movies produce **1,408 movie/genre rows**. A movie may belong to several genres, so totals across genres overlap.

The rating regression is compared against a training-mean baseline on the same fixed 80/20 split:

| Model | Test MSE |
| --- | ---: |
| Linear regression | 2.467321 |
| Training-mean baseline | 2.630154 |

This modest improvement on one split does not establish external generalization. Only the genre-summary and regression cells were rerun against the tracked CSV. Edited-cell outputs were cleared after changes; the complete live workflow was not rerun.

Redundant embedded Plotly JavaScript outputs were removed from the summary-chart cell, reducing the notebook from about 14.5 MB to **0.10 MB**. Re-render charts locally. The previously linked screenshot was not tracked and has been removed from the documentation.

## License

[MIT](LICENSE) for source code; TMDB data and API access conditions are separate.
