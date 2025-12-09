# Interim Analysis for A/B Testing

### 📌 Overview
This project evaluates the performance of a marketing nurture email campaign by comparing the response rate between the Test group and the Control group. The goal is to determine whether the Test variant produces a statistically meaningful lift in engagement.

### 🎯 Objectives
To assess significance properly in a repeated-measures setting, we apply sequential analysis techniques—specifically the O’Brien–Fleming (OBF) and Pocock alpha-spending methods.

These approaches:
- Control the overall Type I error rate
- Reduce false positives compared to a traditional fixed α = 0.05
- Provide statistically valid early-stopping guidelines

This ensures that any decision to stop, continue, or adopt the Test version is grounded in rigorous inference rather than noisy short-term fluctuations.

### 📈 Data Sources
The analysis uses the Nurture Email Performance Dataset, which includes: Days to Respond, Group (Test vs. Control), Cumulative Responses, Leads and Cumulative Response Rate.

### 💻 Analytical Approach
We monitor significance over time using both frequentist and Bayesian frameworks:

1. Frequentist Sequential Testing — Observed p-values and Z-statistics are compared against:
- OBF alpha boundary — very conservative early, less strict later
- Pocock boundary — constant significance threshold
- Traditional α = 0.05 — for baseline comparison

2. Bayesian Inference — A daily-updated Beta–Binomial model estimates:
- Posterior mean difference (Test – Control)
- 95% credible intervals
- Posterior probability that Test is better than Control

### 📁 Key Findings
1. P-value vs. Sequential Alpha Boundaries
- The p-value curve never crosses any of the sequential alpha thresholds.
- There is no frequentist evidence of a statistically significant lift.

2. Z-statistic vs. Z-Boundaries
- Z-scores remain far below the OBF and Pocock critical values at all time points.
- This confirms the p-value conclusion: no early-stopping signal.

3. Bayesian Posterior Mean & 95% CI
- Posterior mean difference remains approximately zero throughout the monitoring period.
- The 95% credible interval consistently includes zero.
- Bayesian evidence indicates no meaningful lift from the Test group.

4. Posterior Probability Test > Control
- The posterior probability that Test outperforms Control remains around 0.50–0.55.
- This is well below typical decision thresholds (e.g., 0.90, 0.95, 0.99).
- Bayesian decision rules therefore do not support declaring the Test as a winner.

### 📑 Recommendations
1. Continue the Experiment
Current evidence—frequentist and Bayesian—does not support stopping or adopting the Test version.

2. Consider Increasing Sample Size or Duration
If the expected lift is small, additional data are needed to achieve adequate statistical power.

3. Re-evaluate After More Data Accumulate
Ongoing sequential monitoring will remain valid and will help ensure decisions are data-driven and defensible.
