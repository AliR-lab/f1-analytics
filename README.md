# F1 Analytics

A hands-on learning project in data analytics, big data and AI, using Formula 1 as the common thread. Each case answers a real question with real data, step by step, from simple analysis on my laptop to pipelines, machine learning and real-time telemetry.

[![F1 Dominance dashboard](figures/dashboard_preview.png)](https://alir-lab.github.io/f1-analytics/)

## Cases

| # | Question | Explore | Status |
|---|---|---|---|
| 1 | Which teams dominated each era of F1? | [Dashboard](https://alir-lab.github.io/f1-analytics/) · [Report](https://alir-lab.github.io/f1-analytics/report.html) · [Notebook](notebooks/01_dominant_teams.ipynb) | ✅ Done |
| 2 | Who is the best driver once you remove the effect of the car? | Coming soon | 🟡 In progress |

### Case 1 in a nutshell

Dominance measured as the percentage of races won each season (1950-2026), seen from three angles: teams, engines and factories. The highest peak of all belongs to an engine, the Ford Cosworth (87.8% in 1973), just above Mercedes in 2014-2016 (86.3%).

## Repository structure

| Path | Content |
|---|---|
| `notebooks/` | One notebook per case, numbered (`01_`, `02_`…) |
| `dashboard/` | HTML templates of the web pages |
| `docs/` | The generated website, published with GitHub Pages |
| `figures/` | Static charts and images |

## Tech stack

- **Python 3.13**, managed with [uv](https://docs.astral.sh/uv/)
- **pandas** and **DuckDB** for data analysis
- **matplotlib** and **Plotly** for charts
- **JupyterLab** for exploration
- HTML, CSS and JavaScript for the website, built with the help of Claude Code

## Reproduce

1. Clone the repo and install the environment: `uv sync`
2. Download `f1db-csv.zip` from the [F1DB releases](https://github.com/f1db/f1db/releases) (v2026.20.0) and unzip it into `data/raw/f1db/`
3. Run any notebook from top to bottom: `uv run jupyter lab`

## Data

Data from [F1DB](https://github.com/f1db/f1db), licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Raw data is not included in this repository.