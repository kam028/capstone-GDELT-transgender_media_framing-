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

### Code
\```r
#Create contingency table
theme_tone_table <- table(master_long$theme, master_long$tone_label)

#Run chi-square test
chi_result <- chisq.test(theme_tone_table)
chi_result
Output
- Chi-square statistic:353438
- df: 13108
- p-value: < 2.2e-16

multinom_model <- multinom(
  tone_label ~ TAX_FNCACT + LGBT + BAN + LEGISLATION +
    WB_615_GENDER + GENERAL_HEALTH + EDUCATION +
    EPU_POLICY + USPEC_POLITICS_GENERAL1 +
    CRISISLEX_C03_WELLBEING_HEALTH + MEDICAL + TRIAL,
  data = article_sample,
  trace = FALSE
)

summary(multinom_model)


![Effect of GDELT Themes on Article Tone](figures/theme_effects_coefficients.png)


