# Interim Analysis for A/B Testing


1. Data Loading and Preparation
- Imported the synthetic dataset containing the daily response rate of both test and control groups.
- Ensured each day has both groups represented.

2. Frequentist Interim Analysis
- Computed cumulative mean differences between test and control groups.
- Calculated standard errors and Z-scores for each interim look.
- Applied an O'Brien-Fleming group sequential monitoring boundary to control Type I error inflation.
- Generated p-values at each interim checkpoint.
- Identified the crossover where the test group initially leads (Days 1–50), then the control group
overtakes (Day 51 onward).
How to interpret
If the Z-score crosses the dashed boundary, the effect (test > control) is strong enough to justify early stopping for efficacy.


If the Z-score remains below the boundary, the evidence is not yet strong enough for early stopping.


3. Bayesian Interim Analysis
- Implemented normal–normal conjugate updating with prior variance t² = 1.0.
- Computed posterior mean, posterior variance, and 95% credible intervals.
- Estimated posterior probability that the test group outperforms control at each interim look.
How to interpret
When the entire shaded interval is above zero, there's strong evidence test > control.


When it includes zero, the data are inconclusive.


When it's below zero, the control appears better.
4. Posterior Probability That Test > Control
This curve gives the probability, given all data so far, that the test group outperforms the control group.

How to interpret
Values near 1.0 → strong belief test is better.


Values near 0.5 → no meaningful difference.


Values near 0.0 → strong belief control is better.



4. Insights
- The cumulative response rates show an expected pattern: test group dominates early, then control group surpasses late.
- Frequentist Z-curve stays below the O'Brien-Fleming boundary, suggesting no early stopping signal.
- Bayesian posterior probability increases early but declines after the crossover point.
- Posterior credible intervals narrow as more data accumulate, improving certainty about the treatment difference.

