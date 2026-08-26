# FlyRank Capstone — Build Write-up

## What I built

I built a search-intelligence machine-learning workflow for identifying content that shows signs of decline and for prioritizing which content should receive attention.

The task was framed as binary classification using `is_declining_label` as the target/proxy and ROC-AUC as the primary evaluation metric. The workflow combines large-scale data preparation, feature engineering, an interpretable baseline, ML evaluation, and action-oriented interpretation.

## Who it is for

The intended users are people working with content and search performance who need a systematic way to identify potentially declining pages and decide where review or refresh effort should be focused.

The output is decision support, not an automatic replacement for human judgment.

## Stack and why

- **Python** — flexible for data preparation, modelling, evaluation, and automation.
- **Google Colab** — convenient for notebook-based development and access to compute without requiring a complex local environment.
- **Pandas / NumPy** — data manipulation and numerical processing.
- **scikit-learn** — classical ML modelling and evaluation.
- **Hugging Face datasets / parquet tooling** — access and processing of the large warehouse release.
- **Matplotlib** — evaluation and diagnostic visualizations.
- **GitHub** — versioned source, documentation, and public submission package.

I chose a notebook-centered workflow because it made each stage inspectable while working through the internship assignments.

## Data

The project used the FlyRank internship warehouse, including the `fact_content_daily_performance` dataset/configuration. The development work focused on March 2026 data and reached approximately 78.8 million processed examples.

Important signals included search volume, impressions, recent versus previous impressions, days with impressions, content freshness, CTR, and average search position.

The full warehouse is access-controlled. No private credentials should be committed to this repository.

## Architecture

```text
                 FlyRank warehouse
                        |
                        v
              Data loading / access
                        |
                        v
              Data validation
                        |
                        v
             Feature preparation
                        |
             +----------+----------+
             |                     |
             v                     v
       Rule-based baseline      ML model
             |                     |
             +----------+----------+
                        |
                        v
                    Evaluation
                        |
                        v
             Results / interpretation
                        |
                        v
              Review / refresh actions
```

## Baseline design

Before using a more complex ML approach, I built a transparent baseline using content staleness and impression decline.

The baseline produced an action score and mapped content into:

- `REFRESH_NOW`
- `REVIEW`
- `MONITOR`

The purpose was to create a simple benchmark that could be understood without a trained model.

## Evaluation

The primary metric is **ROC-AUC**.

The exact final values should come directly from the verified final evaluation notebook:

- **Baseline ROC-AUC:** `[VERIFY FROM FINAL NOTEBOOK]`
- **V2 ROC-AUC:** `[VERIFY FROM FINAL NOTEBOOK]`

I am leaving these as verification fields rather than inventing numbers. The final repository should contain the exact measured values before portal submission.

## Hardest thing that broke

The most difficult part was working with the large warehouse workflow and getting data access, loading, and processing to work reliably. Authentication and large parquet data introduced problems that were not present in the small starter dataset.

The practical lesson was that data engineering and debugging are part of ML engineering. A model cannot be evaluated until the data pipeline is reliable, and a successful-looking notebook cell is not enough unless its output is checked.

## What I would build next

The next version would evaluate the approach across multiple time periods instead of relying on one development period. I would also compare performance across different content/client segments and connect predictions to business outcomes such as the value of a successful refresh.

A longer-term version could become a monitoring application that periodically scores content, surfaces the highest-priority items, explains the main signals behind each recommendation, and allows a human reviewer to record whether the recommendation was useful.

## Limitations

- The target is a proxy for content decline and may not represent every business definition.
- Historical performance can change as search behavior and ranking systems change.
- The full dataset is access-controlled, which limits independent reproduction.
- A prediction should not automatically trigger a content change without human or business validation.
- Model performance may vary across clients, markets, content types, and future periods.

## AI involvement

AI assistants were used as development and reasoning partners. They helped with explanations of unfamiliar concepts, debugging suggestions, code structure, documentation, and review.

I still tested and reviewed the work myself. I ran the code, investigated errors, checked notebook execution, and verified outputs before using them in the final package. This distinction matters because AI-generated code or reasoning can be plausible while still being wrong.

## Reproducibility

1. Clone the repository.
2. Follow the existing `SETUP.md` instructions.
3. Use an appropriate Python/Colab environment.
4. Install the required dependencies.
5. Configure any required dataset access through secrets/environment variables.
6. Open the relevant notebook under `work/notebooks/`.
7. Run the notebook cells in order.
8. Compare the resulting evaluation metrics with the values documented in this package.

Never commit access tokens or private data.

## Final note

The project is intentionally presented as a real engineering workflow rather than as a claim that a model can perfectly predict search performance. The strongest part of the work is the complete process: define the problem, understand the data, establish a baseline, build and evaluate the ML approach, identify limitations, and communicate what the result can and cannot support.
