# Melt-Pool Generalization in Metal Additive Manufacturing

This repository contains the reproducibility materials for the manuscript:

**Machine learning for melt-pool prediction in metal additive manufacturing: source-aware evaluation, data quality, and comparison with analytical physics**

## Study overview

This work examines how machine-learning performance for melt-pool prediction changes when evaluation is performed under increasingly deployment-oriented validation protocols.

The principal evaluation protocols are:

- **V0:** random record-level validation
- **V1:** source-study-held-out validation
- **V2:** alloy-held-out validation

Publication/source identity is used as the available provenance proxy for source-aware validation.

## Source data

The study uses the publicly available **MeltpoolNet** dataset introduced by Akbari et al.

For reproducibility, the analyses use the following MeltpoolNet Git commit:

`6d68e2acaad8d074134a7f3d843278649774d661`

The original MeltpoolNet data are not redistributed in this repository. The self-contained validation notebooks obtain the source data directly from the original public repository.

## Reproducibility notebooks

### Data preparation
- `Paper 4 Clean and split.ipynb`  
  Cleans the MeltpoolNet data, defines feature sets, and constructs the frozen evaluation splits.

### Baseline generalization analysis
- `Paper4 03 baselines optimism gap.ipynb`  
  Evaluates the change in model performance across random, source-study-held-out, and alloy-held-out protocols.

### Audited final validation
- `Paper4 07 final validation AUDITED.ipynb`  
  Reproduces the corrected Eagar-Tsai comparison, physical-data audit, LOSO classification analysis, and corrected process maps.

### Final remaining checks
- `Paper4 08 remaining checks SELF CONTAINED.ipynb`  
  Reproduces the final width analysis, uncertainty/selective-prediction analysis, empirical conformal coverage, and Eagar-Tsai-derived defect-mode sensitivity analysis.

## Final results

Final audited outputs are provided under:

- `results/notebook07_audited/`
- `results/notebook08_final/`

These folders contain the summary tables and figures used to verify the final manuscript results.

## Reproduction

The final validation notebooks are designed to run in **Google Colab**.

For the principal corrected analyses:

1. Open `Paper4 07 final validation AUDITED.ipynb` in Google Colab.
2. Select **Runtime → Run all**.
3. Run `Paper4 08 remaining checks SELF CONTAINED.ipynb` in the same way.

The notebooks automatically obtain the required public source data and record the analysis outputs.

## Software

The analyses use Python and packages including:

- NumPy
- pandas
- scikit-learn
- XGBoost
- SciPy
- Matplotlib
- SHAP

A reproducible software-environment file will be included with the archived release.

## License

Code developed specifically for this study is released under the MIT License.

Third-party datasets and software remain subject to their original terms and licenses.

## Citation

Citation information for the associated manuscript and archived software release will be added when the Zenodo DOI is issued.
