# Healthcare Workplace Violence Skill

A Claude skill that studies violence against healthcare workers in U.S. medical facilities. It uses free, public injury data from the Bureau of Labor Statistics (BLS), and it gives the same kind of report every time it runs.

## What the skill does

When you ask Claude to update or summarize the healthcare workplace violence research, the skill:

1. Finds the newest BLS injury tables online (or uses copies you saved).
2. Pulls the violence injury rate for each type of healthcare facility.
3. Builds a table that ranks facility types, a bar chart, and a short report.
4. Checks the results against a published, peer-reviewed study (Lombardi et al., *Health Affairs Scholar*, 2024).
5. Writes a plain-language summary that a hospital manager could act on.

## Questions it answers

1. How has the rate of violence injuries changed for each type of healthcare facility since 2011?
2. Which facility types have the highest rates (for example hospitals, psychiatric hospitals, nursing homes, home health, outpatient clinics)?
3. Which healthcare jobs are most at risk?
4. How does healthcare compare with all private industry?

## What "rate" means here

The number of injuries caused by an intentional injury by another person (BLS event code 111) that led to at least one day away from work, per 10,000 full-time workers. Threats or assaults that did not cause missed work are not counted, so the real amount of violence is higher.

## What's inside the skill file

The file `healthcare-workplace-violence.skill` is a zipped folder that contains:

| File | What it does |
|---|---|
| `SKILL.md` | The instructions Claude follows: the questions, steps, and rules. |
| `scripts/fetch_bls_violence.py` | Collects the violence rates from the BLS tables. |
| `scripts/build_report.py` | Builds the tables, the chart, and the report. |
| `references/lombardi_2024_table1.csv` | Numbers from the published study, used to check the results. |
| `references/sources.md` | Every source, with links and notes on what each dataset can and cannot show. |

The scripts use plain Python and do not need extra installs.

## How to use it

1. Install the skill in Claude (upload the `.skill` file in Claude's skill settings).
2. Ask Claude something like: *"Update the healthcare workplace violence research."*
3. Claude collects the newest data and returns the summary, ranked table, benchmark check, key takeaways, chart, and source list.

If the BLS website blocks the download, Claude will ask you to open the page in your browser, save it, and share the saved file.

## Rules the skill follows

- Every number is given with its source and year. Missing numbers are reported as missing, never guessed.
- Comparisons use the same measure and time period, and changes are measured with multi-year averages.
- It describes the settings and the injured workers only, not the people who caused harm.
- Every report includes a "Known limits and possible bias" section (for example undercounting and reporting differences).

## Data this skill does not use

This skill does **not** use data from Serious Event analysis. Data collected in incident reporting systems for Serious Event analysis is confidential and is never requested, used, or shared. What happened in an event may be shared, but the analysis of what led to it (root causes and contributing factors) may not. The skill uses only public, published data and research.

## Main sources

- Bureau of Labor Statistics, Survey of Occupational Injuries and Illnesses: https://www.bls.gov/iif/
- Lombardi B, Jensen T, Galloway E, Fraher E. "Trends in workplace violence for health care occupations and facilities over the last 10 years." *Health Affairs Scholar*, 2024. https://doi.org/10.1093/haschl/qxae134
