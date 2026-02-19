# Asthma Risk Factors Analysis: A Logistic Regression Study

## 🔬 Project Overview

This epidemiological analysis examines the relationship between smoking behavior and asthma prevalence using data from the California Health Interview Survey (CHIS). The project demonstrates advanced statistical analysis techniques applicable to healthcare data analytics, pharmaceutical research, and clinical data science.

## 📊 Business Value

- **Healthcare Analytics**: Identified key risk factors for asthma using evidence-based statistical methods
- **Process Optimization**: Applied rigorous model validation techniques for reliable predictive analytics
- **Regulatory Compliance**: Followed epidemiological best practices for confounding assessment and model diagnostics

## 🎯 Key Findings

- **Non-smokers** had 10% higher odds of asthma compared to daily smokers (OR = 1.1; 95% CI: 0.91, 1.34)
- **Occasional smokers** had 2% lower odds of asthma compared to daily smokers (OR = 0.98; 95% CI: 0.73, 1.32)
- Age and race were identified as important confounding variables requiring adjustment
- Model demonstrated good fit with non-significant Hosmer-Lemeshow test (p > 0.05)

## 🛠 Technical Skills Demonstrated

### Statistical Analysis
- **Logistic Regression Modeling** - Binary outcome prediction
- **Confounding Assessment** - Variable selection and adjustment
- **Model Validation** - Goodness of fit testing, Cook's distance analysis
- **Effect Modification Testing** - Interaction analysis by demographic factors

### Data Management
- **Data Cleaning & Preprocessing** - Missing data handling, variable recoding
- **Categorical Data Analysis** - Factor level management and reference coding
- **Quality Control** - Outlier detection and influence diagnostics

### Programming & Tools
- **R Programming** - Advanced statistical analysis and modeling
- **R Markdown** - Reproducible research documentation
- **Data Visualization** - ggplot2 for exploratory analysis
- **Version Control** - Git/GitHub for project management

## 📁 Project Structure

```
asthma-risk-analysis/
├── README.md                 # Project overview and documentation
├── analysis/
│   ├── asthma_analysis.Rmd   # Main R Markdown analysis file
│   └── asthma_analysis.html  # Knitted HTML report
├── data/
│   └── README.md             # Data dictionary and sources
└── results/
    ├── model_diagnostics.png # Model validation plots
    └── odds_ratios_table.csv # Final results summary
```

## 🚀 Getting Started

### Prerequisites
```r
# Required packages
install.packages(c("tidyverse", "blorr", "car", "lmtest", 
                   "table1", "odds.n.ends", "naniar"))
```

### Running the Analysis
1. Clone this repository
2. Open `analysis/asthma_analysis.Rmd` in RStudio
3. Knit the document to reproduce all results

## 📈 Statistical Methods

### Primary Analysis
- **Outcome**: Asthma diagnosis (binary)
- **Exposure**: Smoking status (categorical: daily, some days, not at all)
- **Method**: Multivariable logistic regression

### Model Development Process
1. **Univariate Analysis** - Initial exposure-outcome relationship
2. **Confounding Assessment** - Evaluated age, race, and sex
3. **Model Building** - Stepwise addition of confounders
4. **Diagnostics** - Multicollinearity, goodness of fit, influence analysis
5. **Effect Modification** - Tested interactions by sex

### Quality Assurance
- ✅ Variance Inflation Factors < 3 (no multicollinearity)
- ✅ Hosmer-Lemeshow p > 0.05 (good model fit)  
- ✅ Cook's Distance analysis for influential observations
- ✅ Likelihood ratio tests for model comparison

## 🎯 Applications to Healthcare and Data Science

This analysis demonstrates skills directly applicable to various industries:

- **Clinical Research**: Statistical modeling techniques for patient outcome prediction
- **Risk Assessment**: Identification and quantification of factors affecting health outcomes
- **Regulatory Affairs**: Documentation and validation methods for FDA/regulatory submissions
- **Data-Driven Decision Making**: Evidence-based approach to process and outcome optimization
- **Quality Analytics**: Statistical methods for performance monitoring and improvement

## 📊 Results Summary

| Model | Variables | AIC | Pseudo R² | Conclusion |
|-------|-----------|-----|-----------|------------|
| Model 1 | Smoking only | 8,247.3 | 0.001 | Baseline model |
| Model 2 | Smoking + Age + Race | 8,189.6 | 0.008 | Best fit model |

*Final model showed significant improvement over smoking-only model (LR test p < 0.001)*

## 🔗 Connect

This project showcases analytical skills in:
- Healthcare data analysis and epidemiology
- Regulatory-compliant statistical methods  
- Clinical research and validation techniques
- Quality control and risk assessment methodologies
- Pharmaceutical and medical device analytics

Perfect for roles in clinical data science, healthcare analytics, pharmaceutical research, medical device development, and regulatory affairs.

---
**Author: Adashi Odama  
**Contact odamaadashi@gmail.com  
