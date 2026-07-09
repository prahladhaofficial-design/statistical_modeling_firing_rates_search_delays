# Statistical Modeling of Firing Rates and Search Delays

A statistical analysis project relating firing-rate distributions to search-delay behavior through relative entropy, L1 distance, and Gamma-distribution comparisons.

## Overview

Distributional differences can reveal relationships that are not obvious from raw observations. This repository studies how firing-rate distributions relate to inverse average search delay.
The workflow combines script-based analysis, notebook exploration, CSV data, generated figures, and a technical brief.

## Project Design

- Load firing-rate and search-time datasets.
- Compute relative entropy and L1 distances between empirical distributions.
- Relate distribution distances to inverse average search delay.
- Analyze Gamma-distribution behavior using mean and standard-deviation plots.
- Compare empirical CDFs with theoretical Gamma CDFs.

## Key Capabilities

- Relative-entropy distance calculation.
- L1 distance calculation.
- CSV data loading and processing.
- Gamma-distribution analysis.
- Empirical-vs-theoretical CDF comparison.
- Script and notebook execution paths.

## Repository Structure

```text
src/statistical_modeling.py           Script implementation.
data/firing_rates.csv                 Firing-rate dataset.
data/search_times.csv                 Search-time dataset.
notebooks/statistical_modeling.ipynb  Notebook workflow.
docs/project-brief.md                 Technical brief.
figures/                              Generated plots.
```

## Running Locally

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python src/statistical_modeling.py
jupyter notebook notebooks/statistical_modeling.ipynb
```

## Results and Artifacts

- Relative entropy versus inverse average search delay plot.
- L1 distance versus inverse average search delay plot.
- Standard deviation versus mean plots for Gamma parameters.
- Empirical CDF versus theoretical Gamma CDF plot.

## Reproducibility Notes

- Keep stochastic simulation seeds fixed when comparing firing-rate and delay distributions.
- Regenerate distribution plots after changing rate, shape, or trial-count assumptions.
- Run notebooks in order so summary statistics correspond to the displayed figures.
- Interpret estimated parameters with uncertainty rather than as exact biological or operational constants.

## Detailed Workflow

- Run the script to regenerate figures from the CSV datasets.
- Open the notebook to inspect calculations step by step.
- Review relative entropy and L1 distance plots together.
- Inspect Gamma-distribution plots for distributional fit behavior.
- Use the technical brief to connect formulas with results.

## Implementation Details

- The script defines reusable distance-calculation helpers.
- CSV files are loaded from local `data/` paths.
- Relative entropy and L1 distance provide complementary views of distribution difference.
- Gamma-distribution analysis is used to compare empirical and theoretical behavior.
- Generated figures are stored under `figures/`.

## Data and Inputs

- `data/firing_rates.csv` contains firing-rate measurements.
- `data/search_times.csv` contains search-delay measurements.
- The analysis relates distributional distance to inverse average search delay.
- Changing either dataset requires regenerating all figures.

## How To Interpret the Results

- Relative entropy emphasizes distributional mismatch in an information-theoretic sense.
- L1 distance provides a direct absolute-difference view.
- Gamma CDF comparisons show how well a theoretical distribution tracks empirical observations.
- Plots should be interpreted together rather than as isolated evidence.

## Limitations and Assumptions

- Statistical conclusions depend on dataset quality and preprocessing.
- Distance measures can be sensitive to binning or distribution estimation choices.
- The current workflow does not include formal confidence intervals.
- Adding tests for distance functions would make future edits safer.


## Review Guide

Use this checklist when reviewing the repository on GitHub:

- Start with the overview to understand the project objective before opening notebooks or source files.
- Read the repository structure section to identify the main entry point.
- Inspect generated outputs before rerunning experiments; they provide a quick view of the current project state.
- Review scripts and notebooks together when both are present, since notebooks often explain decisions while scripts preserve reusable execution paths.
- Check the limitations section before interpreting results too strongly.
- Use the possible extensions section to understand how the project can grow without changing its core purpose.

## Troubleshooting

Common issues and fixes:

- If imports fail, confirm that the virtual environment is activated and dependencies were installed from `requirements.txt`.
- If a notebook cell fails because a variable is missing, restart the kernel and run the notebook from the first cell.
- If a script cannot find a data file, run it from the repository root unless the README gives a different working directory.
- If plots are not regenerated, check that the output folder exists and that the script has write permission.
- If a package version causes errors, create a fresh environment and reinstall dependencies before debugging the source code.
- If GPU-related packages are unavailable, run CPU-compatible sections first and treat heavier deep-learning experiments separately.

## Development Notes

The repository is organized to be understandable before it is optimized. Most code favors clear structure, visible intermediate steps, and saved artifacts over highly compressed implementations. When extending the project, prefer small changes that keep the original experiment reproducible.

Recommended development practices:

- Keep new data files under `data/`, `datasets/`, or the existing local data folder for that project.
- Keep generated figures under `figures/`, `plots/`, `outputs/`, or `results/` depending on the existing convention.
- Add new experiments as separate scripts or clearly labeled notebook sections.
- Avoid overwriting existing outputs unless the experiment is intentionally being refreshed.
- Document any new dependency in `requirements.txt`.
- Prefer relative paths so the repository works after cloning on another machine.

## Project Status

This repository is prepared as a standalone GitHub project. The current version includes the core implementation, documentation, and available artifacts needed to understand the work. Future improvements can focus on stronger automation, more tests, richer visual summaries, and cleaner packaging where appropriate.

## Possible Extensions

- Add statistical confidence intervals for distribution estimates.
- Add command-line arguments for input file paths and output folders.
- Package repeated analysis steps into reusable functions.
- Add tests for distance calculations.

## Tech Stack

Python, NumPy, Pandas, SciPy, Matplotlib, Jupyter Notebook.

## Author

Prahladha, IIT Hyderabad
