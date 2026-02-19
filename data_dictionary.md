# Data Dictionary and Documentation

## Dataset Overview

**Source**: California Health Interview Survey (CHIS)  
**Study Design**: Cross-sectional epidemiological survey  
**Population**: California residents  
**Analysis Sample Size**: 1,847 observations (after excluding missing data)

## Variable Definitions

### Outcome Variable

| Variable | Type | Coding | Description |
|----------|------|--------|-------------|
| `asthma_binary` | Factor | 0 = "NO", 1 = "YES" | Primary outcome: Asthma diagnosis status |

### Primary Exposure

| Variable | Type | Categories | Description |
|----------|------|------------|-------------|
| `smoking` | Factor | "EVERY DAY", "SOME DAYS", "NOT AT ALL" | Self-reported smoking frequency |

### Confounding Variables

| Variable | Type | Categories | Description |
|----------|------|------------|-------------|
| `age_new` | Factor | "18-29", "30-39", "40-49", "50+" | Age groups (recoded from detailed categories) |
| `race` | Factor | "WHITE", "HISPANIC", "BLACK", "ASIAN", "OTHER" | Self-reported race/ethnicity |
| `sex` | Factor | "MALE", "FEMALE" | Biological sex |

## Data Processing Steps

### 1. Missing Data Handling
- Original smoking category "INAPPLICABLE" recoded as missing (NA)
- Complete case analysis performed (listwise deletion)
- Final analysis dataset: n = 1,847 (after removing missing data)

### 2. Variable Recoding

#### Age Variable Recoding
```
Original Categories → New Categories
18-25 YEARS, 26-29 YEARS → 18-29
30-34 YEARS, 35-39 YEARS → 30-39  
40-44 YEARS, 45-49 YEARS → 40-49
50-54 YEARS through 85+ YEARS → 50+
```

#### Asthma Variable Recoding
```
Original → Binary
"NO" → 0 (reference category)
"YES" → 1
```

### 3. Reference Categories for Regression Models
- **Asthma**: "NO" (coded as 0)
- **Smoking**: "EVERY DAY" (reference category in regression)
- **Age**: "18-29" (youngest age group)
- **Race**: Varies by model (typically first alphabetically)
- **Sex**: "FEMALE" (reference category)

## Quality Control Measures

### Data Validation Checks
1. **Cross-tabulation** of original vs. recoded variables
2. **Missing data patterns** assessed before analysis
3. **Range checks** for all variables
4. **Logical consistency** checks between related variables

### Statistical Quality Assurance
1. **Model diagnostics** performed for all regression models
2. **Multicollinearity assessment** using Variance Inflation Factors
3. **Goodness of fit testing** using Hosmer-Lemeshow test
4. **Influential observation detection** using Cook's Distance

## Sample Characteristics

### Demographic Distribution
- **Age Groups**: Fairly distributed across age categories
- **Sex**: Approximately balanced male/female representation  
- **Race/Ethnicity**: Reflects California population diversity
- **Smoking Status**: Majority non-smokers, consistent with population trends

### Outcome Prevalence
- **Asthma prevalence**: Approximately 12% (consistent with national estimates)
- **Missing data rate**: <5% for key variables after initial cleaning

## Analytical Approach

### Primary Analysis
- **Method**: Multivariable logistic regression
- **Outcome**: Binary asthma diagnosis
- **Exposure**: Categorical smoking status
- **Adjustments**: Age, race, sex (as appropriate)

### Model Development Strategy
1. **Univariate analysis**: Exposure-outcome relationship
2. **Confounding assessment**: Individual evaluation of potential confounders
3. **Multivariable modeling**: Combined model with identified confounders
4. **Diagnostic testing**: Model validation and assumption checking
5. **Effect modification testing**: Interaction analysis by key variables

## Limitations and Considerations

### Study Design Limitations
- **Cross-sectional design**: Cannot establish temporal relationships
- **Self-reported data**: Potential for recall and social desirability bias
- **Survey methodology**: Non-response bias possible

### Analytical Limitations  
- **Complete case analysis**: Potential selection bias from missing data exclusion
- **Residual confounding**: Unmeasured confounders may exist
- **Sample size**: Limited power for detecting small effect sizes

## Regulatory and Compliance Notes

### Statistical Standards
- Analysis follows **ICH E9 guidelines** for statistical methodology
- **21 CFR Part 11** compliant documentation practices where applicable
- **Good Clinical Practice (GCP)** principles for data integrity

### Documentation Standards
- **Reproducible research** practices implemented
- **Version control** maintained for all analysis code
- **Audit trail** preserved for regulatory review

## File Structure and Naming Conventions

```
project/
├── data/
│   ├── raw/                     # Original SPSS files
│   └── processed/               # Cleaned analysis datasets
├── analysis/
│   ├── asthma_analysis.Rmd     # Main analysis file
│   ├── asthma_analysis.html    # HTML output report
│   └── supplementary_analysis/ # Additional exploratory work
├── results/
│   ├── tables/                 # Summary tables (CSV format)
│   ├── figures/                # Publication-ready plots (PNG/PDF)
│   └── models/                 # Saved model objects
└── documentation/
    ├── data_dictionary.md      # This file
    ├── analysis_plan.md        # Pre-specified analysis plan
    └── model_diagnostics/      # Detailed diagnostic outputs
```

## Contact and Metadata

**Analysis Date: Spring 2021
**Analyst: Adashi Odama
**Institution: Washington University in St. Louis  
**Software: R version 4.3+ with tidyverse ecosystem  
**Last Updated: `r Sys.Date()`

---

*This data dictionary serves as comprehensive documentation for regulatory compliance and reproducible research practices in healthcare analytics.*
