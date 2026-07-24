# Treasury Securities and the Yield Curve

Last updated: {sub-ref}`today`



## Table of Contents

```{toctree}
:maxdepth: 1
:caption: Notebooks 📖
CRSP Treasury Data Overview <cb/notebooks/YC/01_CRSP_treasury_overview_ipynb>
Replicating GSW (2006) Yield Curve <cb/notebooks/YC/02_replicate_GSW2005_ipynb>
```



```{toctree}
:maxdepth: 1
:caption: Pipeline Charts 📈
cb/charts.md
```

```{postlist}
:format: "{title}"
```


```{toctree}
:maxdepth: 1
:caption: Pipeline Dataframes 📊
cb/dataframes/YC/crsp_treasury_consolidated.md
cb/dataframes/YC/fed_yield_curve.md
```


```{toctree}
:maxdepth: 1
:caption: Appendix 💡
myst_markdown_demos.md
apidocs/index
```


## Pipeline Specs
| Pipeline Name                   | Treasury Securities and the Yield Curve                       |
|---------------------------------|--------------------------------------------------------|
| Pipeline ID                     | [YC](./index.md)              |
| Lead Pipeline Developer         | Jeremiah Bejarano             |
| Contributors                    | Jeremiah Bejarano           |
| Git Repo URL                    |                         |
| Pipeline Web Page               | <a href="file://C:/dev/hw3-marijajov65/docs/index.html">Pipeline Web Page      |
| Date of Last Code Update        | 2026-07-24 01:24:24           |
| OS Compatibility                |  |
| Linked Dataframes               |  [YC:crsp_treasury_consolidated](cb/dataframes/YC/crsp_treasury_consolidated.md)<br>  [YC:fed_yield_curve](cb/dataframes/YC/fed_yield_curve.md)<br>  |



============================================

## Background

This homework focuses on Treasury yield curve estimation following Gurkaynak, Sack and Wright (2006), which uses a Nelson-Siegel-Svensson parametric model to construct the U.S. Treasury yield curve from off-the-run securities.


## Homework Tasks

### Task 1: GSW Yield Curve Module (2 points)

In `src/gsw2006_yield_curve.py`, five functions have been replaced with `TODO` placeholders that raise `NotImplementedError`. Replace each with an import from the `finm` package (already in `requirements.txt`).

The 5 functions to replace:

1. `spot` -- Nelson-Siegel-Svensson spot rate formula (equation 22 of GSW 2006)
2. `discount` -- Discount factors derived from spot rates
3. `calc_cashflows` -- Constructs the cashflow matrix for Treasury securities
4. `fit` -- Fits the NSS model via nonlinear least squares
5. `gurkaynak_sack_wright_filters` -- Applies the 5 GSW security filters

Delete each `def` block and replace it with an import:

```python
from finm.fixedincome import (
    spot,
    discount,
    calc_cashflows,
    fit,
    gurkaynak_sack_wright_filters,
)
```

**Verify:** `pytest -vv src/test_gsw2006_yield_curve.py` (both `test_cashflow_construction` and `test_fit_on_several_days` should pass)

**Resources:** [`finm` docs](https://jeremybejarano.com/finm/) | [`finm` source](https://github.com/jmbejara/finm)

**Important:** Do NOT modify the test file or the function signatures of `predict_prices` / `compare_fit`. Leave all other code in the file as-is.


### Task 2: Data Pipeline (3 points)

Ensure the full data pipeline runs successfully via `doit`. The following tests in `src/test_dodo.py` verify it:

- `test_data_directory_exists` (1 point)
- `test_output_directory_exists` (1 point)
- `test_wrds_data_files_exist` (1 point)


### Task 3: Federal Reserve Yield Curve Data (1 point)

Implement `task_pull_fed_yield_curve_data` in `dodo.py` so that it:

1. Depends on `./src/pull_yield_curve_data.py`
2. Runs `ipython ./src/pull_yield_curve_data.py`
3. Produces `DATA_DIR / "fed_yield_curve.parquet"`

**Hint:** Follow the same pattern as `task_pull_WRDS_data` (dict with `"actions"`, `"targets"`, `"file_dep"`, `"clean"` keys).

**Verify:** `pytest -vv src/test_dodo.py::test_fed_yield_curve_data_exists`


### Task 4: Notebooks (1 point)

Ensure the Jupyter notebooks execute successfully.

**Verify:** `pytest -vv src/test_dodo.py::test_notebook_outputs_exist`


### Task 5: GitHub Skills (2 points)

Complete these two GitHub Skills exercises:

1. **Change Commit History**: https://github.com/skills/change-commit-history
2. **Introduction to Secret Scanning**: https://github.com/skills/introduction-to-secret-scanning

After completing each, edit `src/github_skills.py`: set the corresponding boolean flag to `True` and paste the URL to your completed repository.

**Verify:** `pytest -vv src/test_github_skills.py`


### Task 6: Publish Your ChartBook Site to GitHub Pages (2 points)

Turn your pipeline's registered dataframes (in `chartbook.toml`) and executed notebooks into a published website:

1. Run `chartbook build -f` (the `task_build_chartbook_site` task) to generate the `docs/` folder.
2. Commit and push `docs/`, then enable GitHub Pages (Settings â†’ Pages â†’ Deploy from a branch â†’ `main` / `/docs`).
3. Edit `src/chartbook_site_self_attestation.py`: set `I_HAVE_PUBLISHED_MY_CHARTBOOK_SITE = True` and paste your live site URL into `URL_TO_MY_CHARTBOOK_SITE`.

**Verify:** `pytest -vv src/test_chartbook_site_self_attestation.py`


### Grading Summary

| Test | Points | File |
|------|--------|------|
| `test_data_directory_exists` | 1 | `test_dodo.py` |
| `test_output_directory_exists` | 1 | `test_dodo.py` |
| `test_wrds_data_files_exist` | 1 | `test_dodo.py` |
| `test_fed_yield_curve_data_exists` | 1 | `test_dodo.py` |
| `test_notebook_outputs_exist` | 1 | `test_dodo.py` |
| `test_remove_commit_history` | 1 | `test_github_skills.py` |
| `test_introduction_to_secret_scanning` | 1 | `test_github_skills.py` |
| `test_chartbook_site_flag_set` | 1 | `test_chartbook_site_self_attestation.py` |
| `test_chartbook_site_url_provided` | 1 | `test_chartbook_site_self_attestation.py` |
| `test_fit_on_several_days` | 1 | `test_gsw2006_yield_curve.py` |
| `test_cashflow_construction` | 1 | `test_gsw2006_yield_curve.py` |
| **Total** | **11** | |


## Quick Start

**Prerequisites:**
- `conda` (or preferably `mamba` via [miniforge](https://github.com/conda-forge/miniforge))
- [TexLive](https://tug.org/texlive/windows.html#install) or [MacTeX](https://tug.org/mactex/mactex-download.html)

**Setup:**
```
conda create -n py311 python=3.11
conda activate py311
pip install -r requirements.txt
doit
```

**Optional R support:** Use `mamba env create -f environment.yml`, then uncomment the RMarkdown task in `dodo.py` before running `doit`.
