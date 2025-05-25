# Comparing Methods for Missing Data (HIV cohort)

This project compares **four ways of handling missing covariate data**

| Method | R package | Brief note |
|--------|-----------|------------|
| Complete-case analysis (CCA) | _base_ | Drops all rows with any NA |
| Single imputation (mean / mode) | `tidyr` | Quick but under-estimates SEs |
| Multiple imputation (MI) | `mice` | 10 × chained equations |
| Fully Bayesian imputation | `JointAI` | Joint model via MCMC |

Target variable\
`detectable_vl` — viral load is detectable (`log_virus > 0`)

Data set\
`data/CHAIN.csv` — 508 PLHIV, eight predictors (age, HAART adherence, CD4, …).

---

## Quick-start

```r
## ①  clone the repo
## ②  in R (4.2+):

install.packages("renv")          # run once
renv::restore()                   # installs packages from renv.lock

rmarkdown::render(
  "Comparing Methods for Missing Data.Rmd",
  output_dir = "docs"
)
# knitted report appears at docs/Comparing-Methods-for-Missing-Data.pdf or at this link https://github.com/adamlewis-97/Comparing-Methods-for-Missing-Data/raw/main/docs/Comparing-Methods-for-Missing-Data.pdf
