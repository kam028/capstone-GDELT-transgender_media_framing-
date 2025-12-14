# GitHub Link ML — Machine Learning Component

This page documents the machine learning component of my capstone project,
**Who Tells the Transgender Story?**, which analyzes how transgender people are framed
in U.S. news coverage using data from the GDELT global news database (2021–2025).

---

## 1) Machine Learning Question
Can article **themes alone** predict whether a news story about transgender topics
is framed as **negative, neutral, or positive** in tone?

The goal is **not** to build a production prediction system, but to understand
which topics and themes are most strongly associated with hostile framing.

---

## 2) Data, Features, and Labels

- **Target variable:** `tone_label`  
  - negative  
  - neutral  
  - positive  

Tone labels were derived from GDELT’s numeric `tone_mean` score:
- tone_mean < -1 → negative  
- tone_mean > 1 → positive  
- otherwise → neutral  

- **Features:** Binary indicators for GDELT theme tags  
  (e.g., `BAN`, `LEGISLATION`, `WB_615_GENDER`, `GENERAL_HEALTH`,
  `EDUCATION`, `CRISISLEX_C03_WELLBEING_HEALTH`, etc.)

These features capture *what the article is about*, not how it is written.

---

## 3) Models Used

---

### Naïve Bayes (Theme-Based Model)
A Naïve Bayes classifier was trained using **theme indicators only**.

- **Train/Test split:** 70/15/15
- **Accuracy:** ≈66%
- **Macro F1:** ≈0.53

Its value lies in **interpretability**, not raw accuracy.

---

## 4) Why the Theme-Based Model Matters

Although the Naïve Bayes classifier is noisier, it allows me to answer a more
important question:

> *Which themes tend to push coverage toward negative versus positive tone?*

After training, the model produces weights that indicate how strongly each theme
is associated with negative, neutral, or positive coverage. These ranked theme
lists are then used as inputs for:

- Chi-square tests
- Multinomial logistic regression
- Dashboard storytelling and interpretation

In other words, machine learning is used here as an **exploratory and ranking tool**,
not a final decision-maker.

## 4b) Outlet Clustering (Unsupervised Learning)

In addition to supervised classification, I used **k-means clustering** to explore
whether news outlets naturally group into distinct “information worlds” based on
their overall tone patterns.

### Approach
- Each outlet was represented by aggregated tone statistics across its articles.
- K-means clustering was applied to group outlets with similar tone profiles.
- The number of clusters was chosen to balance interpretability with separation.

### Purpose
The goal of clustering was **exploratory**, not predictive. Rather than labeling
individual articles, clustering helps reveal whether certain outlets consistently
produce more negative, mixed, or more neutral/positive coverage of transgender topics.

### Interpretation
The resulting clusters suggest that negative framing is not evenly distributed
across outlets. Some outlets cluster around predominantly negative coverage, while
others show more mixed or relatively neutral patterns. This supports the broader
finding that hostile framing is **structured and concentrated**, not random noise.

These clusters are used to contextualize dashboard views and support later statistical
analysis rather than to make outlet-level predictions.

---

## 5) Interpretation 

The machine learning results reinforce a key pattern seen throughout the project:

- Themes related to **bans, trials, crisis language, and national politics**
  are most strongly associated with negative coverage.
- Themes related to **health care, education, and gender equality**
  are more likely to appear in neutral or positive stories, but occur less often overall.

The ML models help surface these patterns systematically, supporting later
statistical testing and narrative analysis.

---

## 6) Notebook

The full machine learning workflow, including data preparation, model training,
and evaluation, is documented in the following notebook:

- `notebooks/wide_machine_learning.ipynb`
