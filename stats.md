# GitHub Link Stats — Capstone Statistical Testing

This page documents the statistical testing portion of my capstone project: **Who Tells the Transgender Story?**  
Dataset: GDELT transgender-related articles (U.S.-linked, 2021–2025).

---

## 1) Research Question
Do certain GDELT themes appear disproportionately in **negative vs neutral vs positive** coverage?

---

## 2) Variables
- **tone_mean** (numeric): GDELT tone score  
- **tone_label** (categorical): negative / neutral / positive  
- **theme**: GDELT theme tag

Tone labeling rules:
- tone_mean < -1 → negative  
- tone_mean > 1 → positive  
- else → neutral

---

## 3) Chi-Square Test: Theme × Tone
**Why:** Tests whether theme and tone category are independent.


Data not uploaded due to size; code provided for transparency.
