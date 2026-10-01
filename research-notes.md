# Week 6 research notes: violence against healthcare workers

Findings gathered in the Week 6 homework thread (2026-09-30). Every source below was checked against the source itself unless marked otherwise.

## Ground rule

Data collected in incident reporting systems related to Serious Event analysis may not be obtained or shared. What happened in an event can be shared; the analysis of what led to it cannot. Use only public, published data and literature.

## Main data source

- Bureau of Labor Statistics, Survey of Occupational Injuries and Illnesses (SOII). Measure: "intentional injury by other person" (event code 111) with at least one day away from work, per 10,000 full-time workers. https://www.bls.gov/iif/
- Latest BLS release: 2023-2024 (January 22, 2026). No 2023-2024 workplace violence fact sheet yet. https://www.bls.gov/news.release/osh.nr0.htm
- bls.gov is blocked by this project's network settings; add it under Project settings > Network access to pull tables directly.

## Benchmark article

Lombardi B, Jensen T, Galloway E, Fraher E. "Trends in workplace violence for health care occupations and facilities over the last 10 years." Health Affairs Scholar. 2024;2(12):qxae134. https://doi.org/10.1093/haschl/qxae134
- About 30% increase across facility types, 2011 to 2021/2022; rise began before COVID.
- General medical and surgical hospitals 5.0 to 12.9 per 10,000; psychiatric and substance abuse hospitals about 110.
- Table 1 stored in `healthcare-workplace-violence/references/lombardi_2024_table1.csv`.
- Spot check: BLS 2018 fact sheet matches Table 1 for psychiatric hospitals (124.9).

## Dataset review (checked against each source)

See `healthcare-workplace-violence/references/sources.md`. Only BLS isolates healthcare workers; NEISS-AIP, NIBRS, HCUP, PA-PSRS, NVDRS/WISQARS, and CMS are context only.

## Definitions

BLS event code 111 (counted here); OSHA and NIOSH workplace violence; Joint Commission sentinel event (includes rape, assault with serious harm, or homicide of a staff member on site; Sentinel Event Alert 59, 2018). Details in `sources.md` and on the dashboard.

## Contributing factors (published literature)

- Crowding: violent days averaged 95% ED occupancy vs 86% on non-violent days; odds ratio 4.29 (Medley et al., J Emerg Med, 2012; 278 incidents, 220,004 patients). https://www.sciencedirect.com/science/article/abs/pii/S0736467911011486
- Wait times: review of 25 studies; "extended waiting times represent a unique risk factor in EDs" (Xie et al., J Adv Nurs, 2025).
- Organizational factors named by the Joint Commission: long waits or crowding, understaffing, inadequate security and mental health staff, working alone, lack of community mental health services (Sentinel Event Alert 59, 2018).
- Perpetrators at one urban ED, 2023: 37% intoxicated, 29% active psychiatric complaint, 53% neither (Doehring et al., Healthcare, 2026). Insurance and wait time not studied.
- Cost: $18.27 billion a year to U.S. hospitals, 2023 (American Hospital Association, 2025).
- No published study found linking perpetrator insurance status to violence against staff.

## Reporting by age and experience

- Younger age associated with more reporting; reporting rose from 44.9% (2022) to 55.3% (2023); employers responded less than half the time (Friese et al., Nursing Outlook, 2024; Michigan, about 8,000 nurses).
- Only 16% of incidents formally reported; many nurses called violence "just part of the job" (Chapman et al., J Clin Nurs, 2010; Australia; not compared by age).
- Novice nurses (2 years or less) about 1.7 times as likely to face violence (Yang et al., BMC Nursing, 2025; Taiwan).
- Nurse.org 2026 survey (not peer reviewed): 37% of nurses aged 25 to 29 physically assaulted vs 20% aged 65+; 54% reported.
- Caution: younger nurses may report more partly because they face more violence.

## Files in this folder

- `week6-skill-guide.md`: step-by-step prompts for the assignment
- `healthcare-workplace-violence/` and `healthcare-workplace-violence.skill`: the skill
- `workplace-violence-dashboard.html`: interactive dashboard
- `sample-output/`: sample report from the skill
