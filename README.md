# Thalassemia Patient Analysis

## What I wanted to find out
How do treatment, lab results and family income relate to how well thalassemia patients are doing?

## Data
Bangladesh Thalassemia Dataset (Mendeley Data, DOI: 10.17632/8kcdkxmcjw.1)
617 patients from one diagnostic centre, collected March to June 2025.
Download link: https://data.mendeley.com/datasets/8kcdkxmcjw/1

**Credit:** Shahriar Siddique Ayon, Md. Ebrahim Hossain, M Saef Ullah Miah,
B. M. Mredul Arafin, Antara Chowdhury, Nuzhat Noor Islam Prova.
Licensed under CC BY 4.0 (https://creativecommons.org/licenses/by/4.0/).

**Changes made:** `Data/raw` is the original file. `Data/processed/clean.csv`
is my modified version, with added columns (age groups, income bands,
ferritin risk groups, data-quality flags) and two travel-time values set to missing.

## Tools used
- Python (pandas, scipy, seaborn, matplotlib) in a Jupyter notebook
- Excel (pivot tables, slicers, pivot chart)

## What I did
1. Loaded the data and checked its quality.
2. Cleaned it:
   - Kept real answers like "None" and "N/A" instead of treating them as missing.
   - Removed a stray space in one drug name ("DFX ").
   - Flagged suspicious records instead of deleting them.
   - Merged "Low" into "Mild" for school/work impact (only 5 patients).
3. Created new columns: age groups, income bands, ferritin risk groups.
4. Compared groups with statistical tests suited to skewed data, and checked results within each thalassemia type.
5. Built an Excel dashboard with slicers.

## What I found
1. **Thalassemia type matters most.** Median ferritin (iron stored in the body) was about 125 ng/mL for Minor, 920 for Intermedia and 3,700 for Major. Median transfusions were 0, 1.4 and 6.2 units per month.
2. **Adherence and ferritin.** Among Major patients taking iron-removing (chelation) medicine, better adherence went with lower ferritin (Spearman correlation -0.50, p < 0.001). Median ferritin was 2,850 for High, 3,700 for Medium and 4,450 for Low adherence. The pattern also appeared among patients on one drug (DFX) alone.
3. **Drug regimen.** At the same (Medium) adherence level, ferritin differed between DFP and DFX + DFP (p < 0.0001). DFX did not differ significantly from either. This does not prove one regimen is better.
4. **Income and mental health.** Poor mental health looked strongly linked to low income overall, but most of this came from thalassemia type: all 163 Major patients reported poor and all 152 Minor patients reported good mental health. Within the Intermedia group alone, poor mental health still fell from the Low to the Middle income band (98.6%, 77.2%, 57.5%; p < 0.001).
5. **A treated vs untreated chelation comparison was not possible.** Every untreated Intermedia or Major patient (18 in total) also had an adherence rating, which contradicts itself.

## Recommendation
Focus adherence support on Major patients, especially those on combination therapy (25 of the 28 Low-adherence Major patients). Also review how adherence is recorded, because some records contradict each other.

## Limits of this analysis
- It is a one-time snapshot from one centre, so it shows links, not causes.
- Dose, treatment duration and starting ferritin
