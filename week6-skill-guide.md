# Week 6 Homework Guide: Build a Skill on Violence Against Healthcare Workers

Topic: **Harm to people in medical facilities caused by workplace violence** (assaults on nurses, aides, and other staff by patients or visitors).

Copy each gray box exactly. Replace anything in `[brackets]`.

---

## Step 1. Free public data sources

| Source | What it gives you | Where |
|---|---|---|
| **BLS Injuries, Illnesses, and Fatalities (IIF)** | Nonfatal injuries with days away from work caused by "violence by other persons," broken out by industry (hospitals, nursing homes) and job (RNs, nursing assistants, psychiatric aides). Best numeric source. | bls.gov/iif |
| **BLS Census of Fatal Occupational Injuries (CFOI)** | Workplace deaths from homicide/assault in healthcare. | bls.gov/iif (CFOI section) |
| **BLS fact sheet: Workplace Violence in Healthcare** | A short summary with ready-made numbers to check your results against. | search "BLS workplace violence in healthcare fact sheet" |
| **OSHA Healthcare Workplace Violence page** | Prevention guidelines (OSHA 3148) and context for the "why." | osha.gov/healthcare/workplace-violence |
| **CDC / NIOSH** | Risk factors, free NIOSH training, and occupational violence research. | cdc.gov/niosh (search "healthcare workplace violence") |

Tip: BLS is the backbone. Ask Claude to use the most recent year available and to compare healthcare to "all private industry."

---

## Step 2. Research questions (pick 3 to 5)

1. How many healthcare workers were injured by violence at work in the most recent year, and how has that changed over the last 5 to 10 years?
2. Which healthcare settings (hospitals, nursing and residential care, ambulatory care) have the highest *rate* of violence injuries per 10,000 workers?
3. Which jobs are most at risk (registered nurses, nursing assistants, psychiatric aides, home health aides)?
4. How does the violence injury rate in healthcare compare to all private industry and to other high-risk fields like law enforcement?
5. Who is most affected (by sex, age), and how many days away from work does a typical violence injury cause?

Recommended set for the assignment: **1, 2, 3, and 4**.

---

## Step 3. Research in ClaudeChat (claude.ai, a regular chat)

Open a new chat. Send these one at a time. After each answer, use the follow-up prompts until you like the result.

**Prompt 3a (set the stage):**
```
I'm a graduate student researching workplace violence against healthcare workers in the United States. Please use free public data only, mainly the Bureau of Labor Statistics (BLS) Injuries, Illnesses, and Fatalities program, plus OSHA and CDC/NIOSH for context. For every number you give me, cite the source, the table name, and the year. If you cannot find a number, say so instead of estimating.
```

**Prompt 3b (question 1):**
```
Question 1: How many healthcare workers had injuries from violence at work (BLS event category "violence and other injuries by persons or animals," specifically "intentional injury by other person") in the most recent year available? Show a table of the last 5 to 10 years with counts and rates per 10,000 full-time workers.
```

**Prompt 3c (question 2):**
```
Question 2: Break that down by healthcare setting: hospitals, nursing and residential care facilities, and ambulatory health care. Build a table with count and rate per 10,000 workers for each, and rank them from highest to lowest rate.
```

**Prompt 3d (question 3):**
```
Question 3: Which healthcare occupations have the highest number and rate of violence injuries? Include registered nurses, nursing assistants, psychiatric aides, psychiatric technicians, and home health aides. Show a table sorted by rate.
```

**Prompt 3e (question 4):**
```
Question 4: Compare the violence injury rate in healthcare and social assistance with all private industry and with protective service occupations. Show a comparison table and tell me how many times higher healthcare is than the private-industry average.
```

**Follow-up prompts to refine (use any, as often as needed):**
```
Double-check these numbers against the BLS source and list the exact table or link you used.
```
```
Put all results into one clean summary table and add a 3-sentence plain-language summary for a hospital manager.
```
```
Add a short "key takeaways" section and a simple chart of the trend over time.
```

---

## Step 4. Turn the research into a skill (same chat)

```
I'm happy with this research. Please turn it into a reusable Claude skill named "healthcare-workplace-violence". The skill should:
1. Include a SKILL.md with clear instructions describing the research questions, the data sources (BLS IIF, CFOI, OSHA, CDC/NIOSH), and the output format.
2. Include a Python script that collects the latest BLS data (or reads a downloaded BLS table) and builds the summary tables and rates.
3. Produce the same tables, comparison, key takeaways, and plain-language summary we built here, always using the most recent year available and citing sources.
Package it so I can save it to my account and download the .skill file.
```

## Step 5. Save and download

On the skill card Claude shows you, do **both**:
- Click **Save skill**.
- Click **Download** and note where the `.skill` file lands (usually `C:\Users\Kristina\Downloads`).

## Step 6. Test it in a NEW chat

```
Use my healthcare workplace violence skill to update the research.
```

Confirm you get the tables and summary without re-typing the questions.

---

## Steps 7 to 14. Claude Code on your computer

Open a terminal (PowerShell), go to your workspace, and start Claude Code:
```
cd C:\Users\Kristina\Workspace
claude
```
Then paste these prompts one at a time. Wait for each to finish.

**Step 7 (make the folder):**
```
Create a folder called week6-homework inside C:\Users\Kristina\Workspace, so the full path is C:\Users\Kristina\Workspace\week6-homework. Then move into that folder.
```

**Step 8 (make the GitHub repo and link it):**
```
Initialize a git repository in C:\Users\Kristina\Workspace\week6-homework with a main branch. Then create a public GitHub repository called week6-homework under my account winegarkr using the GitHub CLI (gh), and link it as the remote "origin". Do not push anything yet. Tell me if gh is not installed or I'm not logged in.
```
(If Claude says you're not logged in, run `gh auth login` in the terminal and follow the prompts, then repeat the prompt.)

**Step 9 (move the .skill file):**
```
My downloaded skill file is C:\Users\Kristina\Downloads\healthcare-workplace-violence.skill. Move it into C:\Users\Kristina\Workspace\week6-homework. Show me the file name after moving it.
```

**Step 10 (write the README):**
```
Read the .skill file in this folder (it is a zip archive, so unpack it to a temporary location to read it, but do not leave the unpacked files in this folder). Then write a README.md that explains, in plain language: what the skill is about (workplace violence against healthcare workers), the research questions it answers, the public data sources it uses, what files are inside the skill (instructions and scripts) and what each does, and how to run it with a one-sentence prompt in Claude.
```

**Step 11 (commit only the README to main):**
```
Commit ONLY README.md to the main branch with the message "Add README describing healthcare workplace violence skill" and push it to origin main. Do not commit the .skill file.
```

**Step 12 (create the feature branch):**
```
Create a new branch called feature/skill from main and switch to it.
```

**Step 13 (commit and push the .skill file):**
```
On the feature/skill branch, commit the .skill file with a detailed commit message: a short title line, then a paragraph describing what the skill does, the research questions, the data sources (BLS IIF, CFOI, OSHA, CDC/NIOSH), and the files it contains. Push the branch to origin and give me the GitHub link to the .skill file on the feature/skill branch.
```

**Step 14 (check on GitHub):**
Open `https://github.com/winegarkr/week6-homework`, switch the branch dropdown from **main** to **feature/skill**, and confirm the `.skill` file is there. Main should show only the README.

**Deliverable for Canvas:** the link Claude gives you in Step 13. It will look like
`https://github.com/winegarkr/week6-homework/blob/feature/skill/[your-file-name].skill`
(or `https://github.com/winegarkr/week6-homework/tree/feature/skill`).
