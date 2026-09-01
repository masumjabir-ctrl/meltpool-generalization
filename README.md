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

### Final SHAP analysis
- `Paper4_05_SHAP_FINAL_SELF_CONTAINED.ipynb`  
  Reproduces the final source-held-out SHAP attribution analysis used in the manuscript. SHAP is used as a post-hoc physical-consistency check rather than as evidence of causality. The obsolete process-map code from the earlier Notebook 05 is not included; corrected process maps are reproduced by Notebook 07.

### Audited final validation
- `Paper4 07 final validation AUDITED.ipynb`  
  Reproduces the corrected Eagar-Tsai comparison, physical-data audit, LOSO classification analysis, and corrected process maps.

### Final remaining checks
- `Paper4 08 remaining checks SELF CONTAINED.ipynb`  
  Reproduces the final width analysis, uncertainty/selective-prediction analysis, empirical conformal coverage, and Eagar-Tsai-derived defect-mode sensitivity analysis.

## Final results

Final audited and reproducible outputs are provided under:

- `results/notebook05_shap_final/`
- `results/notebook07_audited/`
- `results/notebook08_final/`

These folders contain summary tables, audit information, metadata, and figures used to verify the final manuscript results.

## Reproduction

The final validation notebooks are designed to run in **Google Colab**.

For the principal final analyses:

1. Open `Paper4_05_SHAP_FINAL_SELF_CONTAINED.ipynb` in Google Colab and select **Runtime → Run all**.
2. Run `Paper4 07 final validation AUDITED.ipynb` in the same way.
3. Run `Paper4 08 remaining checks SELF CONTAINED.ipynb` in the same way.

The self-contained final notebooks obtain the required public source data, use the pinned MeltpoolNet source revision, and save the analysis outputs used for manuscript verification.

## Software

The analyses use Python and packages including:

- NumPy
- pandas
- SciPy
- scikit-learn
- XGBoost
- Matplotlib
- PyArrow
- SHAP

Required Python packages are listed in:

`requirements.txt`

## Reproducibility notes

- Source-study identity is treated as the available provenance proxy; it should not be interpreted as a verified laboratory identifier.
- The corrected process-map implementation is contained in Notebook 07.
- The final SHAP implementation is contained in `Paper4_05_SHAP_FINAL_SELF_CONTAINED.ipynb`.
- Raw and calibrated Eagar-Tsai results are reported separately.
- Final validation results should be taken from the audited/final notebooks and result folders rather than superseded intermediate analyses.

## License

Code developed specifically for this study is released under the MIT License.

Third-party datasets and software remain subject to their original terms and licenses.

## Authors

**Abdullah Al Masum Jabir**  
DeVoe School of Business, Technology, & Leadership  
Indiana Wesleyan University, Marion, IN 46953, USA

**Farjana Jahan**  
Department of Biostatistics, Data Science, and Epidemiology  
Augusta University, Augusta, GA 30912, USA

## Citation

Citation metadata are provided in `CITATION.cff`.

The reproducibility package corresponding to this manuscript is permanently archived in Zenodo:

**Version v1.0.0 — DOI: 10.5281/zenodo.22225456**

https://doi.org/10.5281/zenodo.22225456
