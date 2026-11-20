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
| Select Challenge & Define Scope | Confirm Challenge 1 and define how popularity is measured | Italo | In Progress |
| Define Sprint Goal & Risks | Write the sprint goal and document risks with mitigation | Italo | In Progress |
| Set Up GitHub Repository | Create repo, organize folders, initialize README.md | Italo | In Progress |
| _(remaining Kanban tasks)_ | _Add here as they are created on the board_ | Italo | To Do |

## 6. Retrospective
_To be written after project completion._

- What went well?
- What could be improved?
- What should I continue doing in future projects?
