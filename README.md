# Federal FOIA at a glance

A simple Quarto dashboard about how U.S. federal agencies handle Freedom of
Information Act (FOIA) requests, FY2008–2025. Personal prototype for the BU Spark!
DS 701 MuckRock project.

## What it shows

| Tab | Question |
|---|---|
| Requests | How many requests come in and get answered? Is the backlog growing? |
| Speed | How long does an answer take? Which agencies are slowest? |
| Outcomes | Do people get the records they asked for? |
| Appeals & cost | How often do appeals change the answer? What does one answer cost? |

Pick an agency and a year in the sidebar.

## Run it

```bash
pip install pandas jupyter
quarto preview index.qmd    # live preview
quarto render index.qmd     # writes index.html
```

## Data

`data/FY2008.csv` … `data/FY2025.csv`: foia.gov annual report CSVs, merged into one
file per year (one row per agency) by the team's `merge_by_year.py`
(BU-Spark/ds-muckrock-liberation, branch fa26-Tianqi).

- Agency level only, no sub-agencies yet.
- "All agencies" is the sum of all agency rows.
- "<1" day is counted as 0.5; N/A and blanks are left empty.
- Known source gaps: several FY2012 tables are cut short; some tables are missing in
  FY2013, FY2016 and FY2020.

Colors follow the MuckRock data visualization palette.

Built with help from Claude (Anthropic). Check the numbers before using them.
