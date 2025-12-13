# Who Tells the Transgender Story?
## Media Framing of Transgender Issues in U.S. News (GDELT, 2021–2025)

This repository documents my Master’s capstone project for the M.S. in Applied Data Science & Analytics at Howard University.

## Project Overview
This project examines how transgender people are portrayed in U.S. news media and how those portrayals shape public understanding and policy debates. Using more than 160,000 U.S.-linked news articles published between 2021 and 2025, sourced from the GDELT global news database, the project analyzes how often trans-related stories appear, whether they are framed negatively, neutrally, or positively, and which themes, states, and news outlets are most strongly associated with hostile coverage.

Because news coverage is a primary way many people encounter transgender issues, patterns in tone and framing are themselves a social-justice concern. This project provides a data-driven way to identify where negative narratives concentrate and how they spread.

## Methods
- Data extraction and preprocessing using Python
- Deduplication and parsing of GDELT tone and theme fields
- Conversion of numeric tone scores into negative, neutral, and positive labels
- Theme-based classification to identify topics associated with different tones
- Chi-square tests and multinomial logistic regression to estimate the influence of themes, states, and outlets
- K-means clustering to group news outlets by overall framing patterns
- Interactive dashboard development in Tableau for non-technical audiences

## Key Outputs
- Interactive maps and timelines showing where and when trans-related coverage spikes
- Theme rankings associated with negative, neutral, and positive tone
- Outlet clusters representing distinct “information worlds” of coverage

## Interactive Dashboard
Tableau Public:
https://public.tableau.com/app/profile/kaitlin.mitchell2596/viz/CapstoneProject_17647055917570/Dashboard5?publish=yes

## Intended Audience & Use
This project is designed for advocacy organizations, journalists, educators, and researchers interested in understanding how media narratives about transgender people are produced and circulated. The dashboard is intended as an exploratory and awareness-building tool rather than a predictive system.
