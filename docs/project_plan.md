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

> Deliver, by the end of the sprint, a complete analysis of Challenge 1 in a reproducible Jupyter Notebook that identifies which characteristics are associated with more views and higher ratings on Netflix, with at least 3 visualizations, 3 business insights and a documented GitHub repository.

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

Kanban board: `docs/kanban_board.png` (screenshot of the final board, all cards in Done).

| # | Task | Description | Owner | Status |
|---|---|---|---|---|
| 1 | Select Challenge & Define Scope | Confirm Challenge 1 and define how popularity is measured | Italo | Done |
| 2 | Define Sprint Goal & Risks | Write the sprint goal and document risks with mitigation | Italo | Done |
| 3 | Set Up GitHub Repository | Create repo, organize folders, initialize README.md | Italo | Done |
| 4 | Load & Inspect Datasets | Load the three tables and inspect shapes, types, nulls and duplicates | Italo | Done |
| 5 | Clean & Merge Data | Validate missing values, standardize names, durations and dates, parse `cast`, merge tables | Italo | Done |
| 6 | Conduct EDA | Analyze distributions, viewing volume, ratings and title characteristics | Italo | Done |
| 7 | Create Visualizations | Build four labeled charts illustrating patterns behind popular content | Italo | Done |
| 8 | Write Markdown & Business Insights | Add explanatory Markdown, derive five business insights, write conclusions | Italo | Done |
| 9 | Final Notebook Check & Export | Run all cells top to bottom, capture screenshot, export HTML/PDF | Italo | Done |
| 10 | Update GitHub & Checklist | Push final files and verify the submission checklist | Italo | Done |
| 11 | Complete Sprint Retrospective | Write the retrospective | Italo | Done |

## 6. Retrospective

### What went well?
- **Early data validation paid off.** Inspecting the three tables before analyzing them exposed a mislabeled column (`users.genre` actually holds gender), dates stored as text and 32 repeated user–movie pairs. Each issue was handled and documented, and the merge was validated (120 rows preserved, no nulls, no lost movies or users).
- **A measurable definition of popularity.** Defining popularity from `watch_history` (views, unique viewers, average rating, top 25% of titles) kept the analysis focused, and normalizing by number of titles avoided catalog-size bias between genres.
- **Small, well-defined Kanban cards.** Working alone, splitting the project into 11 tasks with a clear "done" for each kept steady progress and made it easy to see what was left.
- **Checks before conclusions.** Before writing insights, I tested whether the duration effect was only a genre effect and whether it held when popularity meant reach instead of views. This made the insights more reliable and the limitations explicit.
- **Reproducible and version-controlled.** The notebook runs from top to bottom without errors and the work lives in a GitHub repository with a README.

### What could be improved?
- **Inspect the data before writing scope and risks.** The first versions of the scope and risks were written before looking at the actual dataset and had to be revised. Next time, a quick look at the data comes first.
- **Small sample.** With 24 titles, 20 users and 120 records, the findings are indications, not proof. I should flag sample-size limits at the start of the project and look for complementary data (for example watch time or completion rate).
- **No second pair of eyes.** Working alone meant there was no peer review of the insights or the charts. Asking a classmate to review the final notebook would catch weak spots.
- **Check visuals earlier.** Some chart labels overlapped and only showed up when reviewing the images. Looking at each chart right after creating it saves rework.

### What should I continue doing in future projects?
- Validate and document data-cleaning decisions early.
- Compare groups on a normalized basis and state limitations honestly.
- Break the work into small Kanban tasks with clear completion criteria.
- Structure notebooks as explanation, code and interpretation.
- Use version control from the first day.
