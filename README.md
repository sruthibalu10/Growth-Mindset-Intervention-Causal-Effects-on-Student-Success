# Growth-Mindset-Intervention-Causal-Effects-on-Student-Success
This project uses R to estimate the causal effect of a growth-mindset intervention on student achievement using regression, IPTW, and doubly robust estimators. All methods yield a positive ATE of approximately 0.41, indicating that the intervention increases achievement scores by about 0.41 units on average.
# Growth Mindset Intervention: Causal Effects on Student Success

This project investigates the causal effect of a growth mindset intervention on student academic achievement using observational data. Because simple comparisons can be biased in non-experimental settings, the analysis applies multiple causal inference methods to estimate an unbiased Average Treatment Effect (ATE).

## 📘 Overview
A growth mindset—the belief that intelligence can develop with effort—has been shown to improve student outcomes. Using a synthetic dataset modeled after the National Study of Learning Mindsets, the goal of this project is to estimate the causal effect of a mindset-focused intervention on achievement, adjusting for confounding factors.

## 🔍 Data Exploration
Before applying causal inference techniques, the dataset was explored to identify key variables, understand their distributions, and examine correlations.

- Achievement showed strong positive correlations with **self-reported confidence** and **test scores**, consistent with the data relationships illustrated in the poster :contentReference[oaicite:1]{index=1}.
- Demographic variables such as poverty level and school race demonstrated moderate associations, suggesting potential sources of confounding.
- Visualization panels in the poster (e.g., regression coefficient plots and correlation heatmaps) highlight these structural patterns.

## 🧩 Causal Assumptions
To ensure valid estimation of the treatment effect, the analysis relies on:

1. **Conditional Ignorability** – After adjusting for observed covariates, treatment assignment behaves as if random.  
2. **Positivity** – Every student has a non-zero probability of receiving either treatment condition.  
3. **Correct Model Specification** – For doubly robust methods, at least one of the models (propensity score or outcome regression) must be correctly specified.

These assumptions are visually reinforced in the poster’s diagrams, particularly the treatment–achievement interaction plot and covariate balance checks :contentReference[oaicite:2]{index=2}.

## 🛠 Methods
Three causal inference approaches were implemented:

### **1. Linear Regression**
Adjusts directly for covariates.  
Estimated ATE ≈ **0.412**.

### **2. Inverse Probability of Treatment Weighting (IPTW)**
Reweights the data using estimated propensity scores to create a pseudo-population mimicking random assignment.  
Estimated ATE ≈ **0.411**.  
The covariate balance plot (see poster) confirms excellent balance after weighting :contentReference[oaicite:3]{index=3}.

### **3. Doubly Robust Estimation**
Combines outcome regression with IPTW to provide a valid estimate if *either* model is correctly specified.  
Estimated ATE ≈ **0.410**.  
Bootstrap results shown in the poster indicate stable and approximately normal sampling behavior :contentReference[oaicite:4]{index=4}.

## 📈 Results
All three methods consistently show:

- A **positive and statistically significant effect** of the growth mindset intervention.
- A tightly clustered set of estimates around **0.41**, indicating robustness.
- Improved comparability between treatment and control groups after weighting.

These findings support the conclusion that the intervention increases student achievement.

## ⚠️ Limitations
- The analysis assumes no unmeasured confounding, which cannot be empirically validated.  
- Generalizability may be limited if the dataset is not broadly representative.  
- Estimates may be sensitive to model misspecification if one or both models are poorly fitted.
