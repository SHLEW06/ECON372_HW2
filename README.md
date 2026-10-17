# ECON 372 — Homework 2

**Shunji Lewandowski — Physician Agency and Payment Changes**

Open `report.html` in a browser to see the full homework with code, output, and figures. GitHub also shows the executed notebook, `code/analysis.ipynb`, directly. The ten parts are answered in order, followed by an appendix of robustness checks.

## Files

- `code/analysis.ipynb`: the executed Python notebook with all written answers.
- `report.html`: a rendered copy of the notebook, with figures embedded.
- `results/`: figures and summary tables produced by the notebook.
- `requirements.txt`: package versions used.
- `input_manifest.json`: checksums of the two input files.
- `data/`: where the course CSV files go (not committed).

## Reproduce

Put `medicare-physician-epidural.csv` and `medicare-physician-ga-office-visits.csv` in `data/`. They come from the course OneDrive and aren't included in this repository.

```bash
python -m pip install -r requirements.txt
python -m jupyter nbconvert --to notebook --execute --inplace code/analysis.ipynb
```

The setup cell checks the input files against the recorded checksums and stops if they differ, since the written answers quote numbers from these exact files. To rebuild `report.html` after editing the notebook:

```bash
python -m jupyter nbconvert --to html --template lab --output-dir . --output report code/analysis.ipynb
```

## Analysis choices

For Q1, the main ranking uses percentage declines among physicians present in all three years with at least 100 injections in 2013; the appendix also ranks by raw decline and tries other cutoffs. For Q2, coding intensity is the share of established-patient visits billed as 99214 or 99215, weighted by service counts, with a check on a fixed set of providers. These are descriptive comparisons, not causal estimates.

I used an AI coding assistant for coding, drafting, and checking. The CMS fact sheet and the course textbook were used for policy and theory background.
