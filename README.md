# FlyRank ML Internship — Final Submission Package

**Participant:** Ikram Khan  
**Track:** General AI Fluency / Applied Search Intelligence  
**Year:** 2026

## Start here

This repository contains my FlyRank ML internship work and final submission package. The project applies machine-learning and search-intelligence methods to large-scale content-performance data to identify content that may be declining and help prioritize review or refresh actions.

### Public links

- **Live portfolio:** https://ikramkhan-gif1.github.io/ikram-portfolio/
- **Deployed paper:** https://ikramkhan-gif1.github.io/FlyRank-ML-Internship/paper/
- **LinkedIn:** https://www.linkedin.com/in/ikram-khan-96200422b/

## Final package

| Deliverable | Location |
|---|---|
| Master index | This README |
| Build write-up | [`submission/build-writeup.md`](submission/build-writeup.md) |
| Final retrospective | [`submission/retrospective.md`](submission/retrospective.md) |
| Build-in-public story | [`submission/build-in-public.md`](submission/build-in-public.md) |
| Final checklist | [`submission/final-checklist.md`](submission/final-checklist.md) |
| Deployed research paper | [`submission/paper_url.txt`](submission/paper_url.txt) |
| Weekly ML notebooks | [`work/notebooks/`](work/notebooks/) |

> **Demo video:** Not included in this package. The FlyRank assignment requires a 3–5 minute live demo, so this remains the one outstanding deliverable if the submission is expected to meet every criterion exactly.

## Project overview

The ML work focuses on search-intelligence data and the problem of identifying content that shows signs of decline. The task was framed as **binary classification**, using `is_declining_label` as the target/proxy and **ROC-AUC** as the primary evaluation metric.

The work used the FlyRank internship warehouse, including `fact_content_daily_performance`. The processed development workflow reached approximately **78.8 million examples**.

### Key signals

`search_volume`, `impressions_90d`, `days_with_impressions`, `impressions_last_30d`, `impressions_prev_30d`, `days_since_last_update`, `ctr`, `avg_position`, `impression_tier`, and `position_tier`.

## Workflow

```text
FlyRank warehouse data
        |
        v
Data loading + validation
        |
        v
Feature preparation
        |
        +----------------------+
        |                      |
        v                      v
Transparent baseline       ML model
        |                      |
        +----------+-----------+
                   |
                   v
             Evaluation
                   |
                   v
       Interpretation + actions
```

## Baseline

A transparent baseline was created before relying on a more complex ML approach. It combined content staleness and impression-decline signals into an action score and mapped results to `REFRESH_NOW`, `REVIEW`, and `MONITOR`.

## Evaluation

**Primary metric:** ROC-AUC  
**V2 ROC-AUC:** *To be filled from the verified final evaluation output.*  
**Baseline ROC-AUC:** *To be filled from the verified baseline evaluation output.*

These values are intentionally not guessed. The final submission should use the exact numbers produced by the submitted evaluation notebook.

## Reproducibility

The work was developed in Python/Colab. Common dependencies include `pandas`, `numpy`, `scikit-learn`, `datasets`, `pyarrow`, and `matplotlib`. The full FlyRank warehouse is access-controlled, so reproduction of the large-data workflow requires appropriate access. Credentials must be supplied through secrets/environment variables and must never be committed.

Open the relevant notebook under `work/notebooks/` and run the cells in order. The repository's existing `SETUP.md` and `GUIDE.md` contain the original environment instructions.

## Limitations

1. **Proxy target:** the declining-content label may not capture every business definition of decline.
2. **Historical period:** future search behavior may differ from the development period.
3. **Access-controlled data:** the full warehouse is not freely public, limiting independent reproduction.
4. **Model-to-action gap:** a model score should support review rather than automatically deciding that content must be changed.
5. **Generalization:** performance may vary across clients, content types, markets, and future periods.

## AI transparency

AI assistants were used as development and reasoning partners for concept explanations, debugging, code-structure suggestions, documentation, and review. I tested the resulting code, investigated errors, checked notebook execution, and reviewed the outputs before using them in the submission. AI assistance was not treated as proof that a result was correct.

## Three transferable lessons

1. **Define the problem before building the model.** The target, unit of analysis, and success metric determine what the model can prove.
2. **Build a baseline first.** A simple, interpretable benchmark gives later ML work context.
3. **Treat debugging, evaluation, and communication as engineering.** A notebook running without errors is not the same as a validated solution.

## Repository map

```text
submission/
├── README.md
├── paper_url.txt
├── build-writeup.md
├── retrospective.md
├── build-in-public.md
└── final-checklist.md

work/notebooks/
└── weekly assignment notebooks
```

## Status

The written final package and public links are included. The **3–5 minute live demo video is intentionally not included**, per my submission choice. The remaining portal actions are the hours log, showcase submission, final review/sign-off, and any required verification/badge step.
