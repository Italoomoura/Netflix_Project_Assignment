# Project Plan – Netflix Content Analysis (Challenge 1)

## 1. Challenge & Scope

**Challenge 1:** What Makes Content Popular on Netflix?
**Business question:** What characteristics are most common among Netflix titles?

**Popularity definition** (using `watch_history.csv`):
- **Views:** number of watch records per title
- **Unique viewers:** distinct users per title
- **Average rating:** mean rating (1–5) per title
- **Views per title by group:** group views ÷ number of titles in the group (avoids catalog-size bias)
- **Popular title:** top 25% of titles by views

**In scope:** genre, duration, release year, director, cast, viewer age and country, trend over time.
**Out of scope:** recommendation engine (Challenge 4), executive dashboard (Challenge 5), global expansion (Challenge 2).

## 2. Sprint Goal

> Deliver, by **22/11/2026**, a complete analysis of Challenge 1 in a reproducible Jupyter Notebook that identifies which characteristics are associated with more views and higher ratings on Netflix, with at least 3 visualizations, 3 business insights and a documented GitHub repository.

## 3. Risks and Mitigation

| # | Risk | Impact | Mitigation |
|---|---|---|---|
| 1 | Very small sample (24 movies, 20 users, 120 views) may produce coincidental patterns | High | State the limitation, present findings as indications, avoid strong claims |
| 2 | Catalog bias: genres have different numbers of titles, so raw view counts mislead | Medium | Normalize by views per title and compare against the catalog average |
| 3 | Working alone: no reviewer and risk of scope creep | Medium | Limit WIP on the Kanban board, set deadlines per card, keep Challenges 2–5 out of scope |

## 4. Data Quality Notes
- `users.genre` holds gender (Male/Female): rename to `gender` before merging with `movies.genre`.
- 40 user–movie pairs repeat with different dates: treated as re-watches; each record counts as one view.
- `date` is text: convert to datetime.

## 5. Project Plan

| Task | Description | Owner | Status |
|---|---|---|---|
| Select Challenge & Define Scope | Confirm Challenge 1 and define how popularity is measured | Italo | Done |
| Define Sprint Goal & Risks | Write the sprint goal and document risks with mitigation | Italo | Done |
| Set Up GitHub Repository | Create repo, organize folders, initialize README.md | Italo | Done |
| Load & Inspect Datasets | Load movies, users, and watch_history into the Jupyter Notebook and inspect shapes, data types, nulls, and duplicates | Italo | Done |
| Clean & Merge Data | Handle missing values, standardize duration and date formats, parse multi-value fields if needed, and merge tables cleanly | Italo | Done |
| Conduct Exploratory Data Analysis (EDA) | Analyze distributions, viewing volume, average ratings, and key title characteristics (genre, duration, release_year, director, cast) | Italo | To Do |
| Create Visualizations | Build at least three clear, properly labeled charts illustrating patterns behind popular content | Italo | To Do |
| Write Markdown & Business Insights | Add explanatory Markdown cells throughout the notebook, derive at least three business insights, and write final conclusions | Italo | To Do |
| Final Notebook Check & Export | Run all cells from top to bottom without errors, capture a completion screenshot, and export PDF/HTML if desired | Italo | To Do |
| Update GitHub & Checklist | Push the completed notebook, screenshot, and updated README.md to GitHub and verify all submission checklist items | Italo | To Do |
| Complete Sprint Retrospective | Fill out the retrospective covering what went well, what could be improved, and what to continue doing in future projects | Italo | To Do |

## 6. Retrospective
_To be written after project completion._

- What went well?
- What could be improved?
- What should I continue doing in future projects?
