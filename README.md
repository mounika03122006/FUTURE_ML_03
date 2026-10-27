# FUTURE_ML_03 - Resume / Candidate Screening System

An NLP-based system that screens, scores and ranks resumes against a job description, and shows which required skills each candidate is missing.

## Problem
Hiring teams receive hundreds of resumes for one role. Reading them all by hand is slow and inconsistent. This project automates the first screening step.

## Dataset
Kaggle Resume Dataset (snehaanbhawal). 300 random resumes were used.
Link: https://www.kaggle.com/datasets/snehaanbhawal/resume-dataset

## Job role used
IT Software Engineer (17 required skills such as Python, Java, SQL, Linux, Git, cloud, communication).

## Approach
1. Clean the resume text (lowercase, remove links, emails, symbols, stopwords).
2. Extract skills by matching against a skills list (skills.csv).
3. Score each resume:
   - Skill match (60%): share of required skills found in the resume.
   - Text similarity (40%): TF-IDF cosine similarity with the job description.
   - Final score = 0.6 x skill match + 0.4 x text similarity.
4. Rank candidates from highest to lowest score.
5. Identify the skill gap: required skills missing from each resume.

## Results
- The top candidate scored 42.3% and matched 10 of 17 required skills.
- The ranking is saved in candidate_ranking.csv with matched and missing skills for every candidate.
- Charts: top10_candidates.png and skill_gap_rank1.png.

## Files
- resume_screening.ipynb : full code and explanation
- candidate_ranking.csv : ranked list of all 300 candidates
- skills.csv : skills list used for extraction
- top10_candidates.png, skill_gap_rank1.png : charts
- requirements.txt : libraries needed

## How to run
1. Download Resume.csv from the Kaggle link above.
2. Install the libraries: pip install -r requirements.txt
3. Open resume_screening.ipynb in Jupyter Notebook and update the path to Resume.csv.
4. Run all cells.

## Limitations
- Skills are found by matching words from a fixed list, so skills written differently may be missed.
- The system ranks by skills found, not by job category, so some non-IT resumes can rank high.
- It supports a human recruiter and should not replace the final decision.

## Tools
Python, pandas, NLTK, scikit-learn, matplotlib, Jupyter Notebook
