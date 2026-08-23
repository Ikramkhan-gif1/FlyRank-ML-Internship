# FlyRank Internship — Final Submission

## Overview

This folder packages the work completed during my FlyRank Machine Learning Internship, with emphasis on applied search intelligence, data contracts, feature analysis, baseline action scoring, validation, and applied ML workflow.

## Problem

The work investigates content-performance signals and how they can support decisions about content that may be declining. The workflow moves from problem framing and data definition through feature analysis, baseline scoring, validation, and action recommendations.

## Intended Users

- Search-intelligence teams
- Content and SEO teams
- Machine-learning practitioners
- Data analysts
- Content-refresh workflows

## Workflow

```text
FlyRank Warehouse Data
        ↓
Problem Framing
        ↓
Data Contract
        ↓
Feature / Signal Analysis
        ↓
Baseline Action Score
        ↓
Model / Validation
        ↓
Action Playbook
        ↓
Evaluation
```

## Data and ML framing

The internship work uses the FlyRank warehouse data and defines a content-performance unit of analysis. The declining-content task is treated as a binary classification problem using `is_declining_label`, with ROC-AUC as the primary ML metric used in the development work.

## Baseline Action Score

The baseline work includes signals such as impression change and content staleness. It produces an interpretable score and action categories:

- `REFRESH_NOW`
- `REVIEW`
- `MONITOR`

The detailed implementation is in `work/notebooks/w04_baseline_score.ipynb`.

## Assignment Evidence

See [INDEX.md](../INDEX.md) for the complete notebook-by-notebook index.

## Evaluation

See [EVALUATION.md](EVALUATION.md). Final V2 metrics must be entered only after the final V2 run is executed and verified; no unverified metric is claimed here.

## Limitations

See [LIMITATIONS.md](LIMITATIONS.md).

## AI Transparency

AI tools were used as development and reasoning assistants for activities such as debugging, technical explanation, documentation, and reviewing implementation approaches. I remained responsible for running and checking the work, interpreting results, and deciding what was submitted.

## Demo

The FlyRank FL-09 checkpoint requires a 3–5 minute live end-to-end demo. The demo has not been added yet. See [DEMO.md](DEMO.md) for the current status.

## Retrospective

See [RETROSPECTIVE.md](RETROSPECTIVE.md).

## Portfolio

- Portfolio: https://ikramkhan-gif1.github.io/ikram-portfolio/
- GitHub portfolio: https://github.com/Ikramkhan-gif1/ikram-portfolio
- LinkedIn: https://www.linkedin.com/in/ikram-khan-96200422/
