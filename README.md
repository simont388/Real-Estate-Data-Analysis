# Real Estate Sales Price Prediction

A regression analysis modeling residential sale price using structural, quality, and location characteristics, built in R/Quarto. Based on the Kutner Appendix C.7 real estate dataset. This repo includes the dataset, the
full qmd file, as well as the rendered pdf without codes.

## Approach

-**Exploratory Analysis** - Examined the response distribution (raw vs log-transformed price), correlation with predictors, and linearity of continuous response/predictor relationships
-**Response Transformation** - Compared SLR diagnostics for 'Price' vs 'log(Price)' against 'Sqft' which was the most correlated predictor
-**Predictor Pool Construction** - Expanded and 11-predictor base set to a 71-term pool including all interaction and quadratic terms
-**Model Selection** - Used BIC-penalized forward and backward selection to arrive at two candidate models
-**Diagnostics** - Checked linearity, normality, and constant-variance assumptions via diagnostic plots; identified influential points, with sensitivity analysis done on the most influential observations
-**Heteroskedasticity Correction** - Fit weighted least squares (WLS) versions of both candidate models using loess-estimated residual variance as weights
-**Model Comparison** - Compared all candidate models by multiples metrics, finally selecting the forward-selection WLS model

## Files
 `final_project.qmd` — full Quarto source (analysis, code, and writeup)
- `final_project.pdf` — rendered report
- `APPENC07.csv` — dataset (Kutner et al., Applied Linear Statistical
  Models, Appendix C.7)

## Requirements

R packages: `dplyr`, `tibble`, `ggplot2`, `GGally`, `corrplot`, `car`,
`leaps`, `patchwork`, `knitr`

## Reproducing

```bash
quarto render final_project.qmd
```
