# Methodology

## 1. Problem framing

The internship work focuses on search intelligence and content-performance analysis. The ML work frames declining content as a binary classification task.

## 2. Data

The development workflow uses the FlyRank internship warehouse data. The unit of analysis used in the work is a unique combination of report date, client, and content.

Relevant signals used across the work include search volume, impressions, recent and previous-period impressions, days since last update, CTR, average position, impression tier, and position tier.

## 3. Data contract

ML-04 defines the expected structure, assumptions, and interpretation of the data used by later steps.

## 4. Signal and feature analysis

The workflow includes a feature-leakage check and signal audit before the baseline/model stages.

## 5. Baseline scoring

ML-07 develops an interpretable baseline using performance-change and staleness-related signals. Derived components include `impression_change_pct`, staleness buckets, `baseline_score`, `reason_code`, and `action`.

## 6. Model and validation

The later notebooks cover model development and validation auditing. ROC-AUC is the primary metric for the declining-content classification framing.

## 7. Action playbook

The work translates analytical/model signals into practical action categories, including `REFRESH_NOW`, `REVIEW`, and `MONITOR`.

## Reproducibility

The original repository setup and assignment notebooks remain available in the repository. Follow the repository README and FlyRank setup documentation for the environment and data-access requirements.
