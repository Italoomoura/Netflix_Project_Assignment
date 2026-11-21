# Netflix Content Analysis – What Makes Content Popular?

Agile data analysis project (Challenge 1) built with Python, pandas and Jupyter.

## Business Question
**What makes content popular on Netflix?** Which characteristics are most common among the titles viewers watch the most and rate the highest?

## Scope & Definition of Popularity
Popularity is measured with viewer behavior from `watch_history.csv`:

| Metric | Definition |
|---|---|
| Views | Number of watch records for a title |
| Unique viewers | Number of distinct users who watched a title |
| Average rating | Mean `rating` (1–5) given to a title |
| Views per title (by group) | Views of a group (e.g. a genre) divided by its number of titles, to avoid catalog-size bias |

A title is considered **popular** if it is in the top 25% by number of views. The analysis compares the characteristics of popular titles (genre, duration, release year, director, cast) and viewer profiles (age, country) with the rest of the catalog.

## Dataset
Located in `data/raw/` (never edited):

| File | Rows | Description |
|---|---|---|
| `movies.csv` | 24 | Title, duration, release year, genre, director, cast |
| `users.csv` | 20 | Age, country, gender (column named `genre` in the raw file) |
| `watch_history.csv` | 120 | Which user watched which movie, rating and date |

## Project Structure
```
netflix-popularity-analysis/
├── data/
│   ├── raw/                # original CSV files
│   └── processed/          # cleaned/merged data
├── notebooks/
│   └── netflix_analysis.ipynb
├── reports/
│   └── figures/            # exported charts, PDF/HTML of the notebook
├── docs/
│   └── project_plan.md     # scope, sprint goal, risks, kanban, retrospective
├── requirements.txt
├── .gitignore
└── README.md
```

## How to Run
```bash
git clone https://github.com/Italoomoura/Netflix_Project_Assignment.git
cd Netflix_Project_Assignment
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
jupyter lab notebooks/netflix_analysis.ipynb
```

## Key Insights
_To be completed after the analysis._

## Limitations
- Small sample (24 movies, 20 users, 120 views): results are indications, not statistical proof.
- Genres have different numbers of titles, so metrics are normalized per title.

## Project Management
Plan, sprint goal, risks and retrospective: [`docs/project_plan.md`](docs/project_plan.md)
