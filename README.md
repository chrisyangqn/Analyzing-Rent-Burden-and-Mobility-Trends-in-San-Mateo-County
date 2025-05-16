# Analyzing Rent Burden and Mobility Trends in San Mateo County

**Authors**:  
- Zhilie Qian ([LinkedIn](https://www.linkedin.com/in/zhilieqian))  
- Qinuo Yang ([LinkedIn](https://www.linkedin.com/in/qinuoyang))  
- Chelsea Javier ([LinkedIn](https://www.linkedin.com/in/chelsjav))

**Course**: COMPSS 224A — *Forced Out: Decoding Housing Displacement through Data*  
**Date**: March, 2025  
**Source Code**: [GitHub Repository](https://github.com/qianzhilie/compss)

---

## Abstract

San Mateo County is grappling with a deepening housing crisis marked by soaring prices and financial strain on renters. This study investigates housing affordability and population movement, using historical trend analysis, spatial mapping, and causal inference to answer:

1. How has the rent burden and geographical mobility in San Mateo County changed over time?
2. To what extent has geographical mobility and rent burden correlated?

Findings show extreme rent burdens correlate with increased relocation, especially for lower-income and immigrant communities.

---

## Table of Contents

- [Introduction](#introduction)
- [Research Method](#research-method)
- [Historical Patterns of Rent Burden and Geographical Mobility](#historical-patterns-of-rent-burden-and-geographical-mobility)
- [Correlation Between Mobility and Rent Burden](#correlation-between-mobility-and-rent-burden)
- [Summary of Results](#summary-of-results)
- [Conclusion](#conclusion)
- [Appendix](#appendix)

---

## Introduction

San Mateo County, transformed by the tech boom, now faces a severe housing crisis. Historical factors, like exclusionary housing policies, and modern pressures from rising rents have led to displacement, especially for marginalized communities.

![Median Household Income](pic/california.png)

> “Many racist housing discrimination policies were birthed in California.” — *Ellis (2021)*

![Research Method](pic/relationship_map.png)

---

## Research Method

This study uses data from the tidycensus R package and employs both descriptive and causal analyses to understand changes in rent burden and mobility over time.

### Research Questions

1. **Trend Analysis**: How have rent burden and mobility evolved?
2. **Correlation**: What is the relationship between mobility and rent burden?

### Rent Burden Categories

| Rent Burden Category     | % Income on Rent |
|--------------------------|------------------|
| Moderately Rent-Burdened | 30–34%           |
| Severely Rent-Burdened   | 35–39%           |
| Highly Rent-Burdened     | 40–49%           |
| Extremely Rent-Burdened  | 50%+             |

---

_(Truncated here for brevity; the full document will continue with figures, tables, analysis, and appendices in markdown format.)_


---

## Historical Patterns of Rent Burden and Geographical Mobility

### Rent Burden

#### Choropleth Maps: 2012 vs. 2022

![Rent Burden 2012](pic/rbr_san_mateo_2012.png)
![Rent Burden 2022](pic/rbr_san_mateo_2022.png)

> These maps suggest an overall decline in rent burden from 2012 to 2022.

#### Mean Rent Burden Over Time

![Mean Rent Burden](pic/rbr_fluctuation.png)

#### Rent Burden by Income

![Rent Burden by Income](pic/rbr_income.png)

---

### Mobility

#### Mobility Trends: 2012 vs. 2022

![Mobility 2012](pic/mobility_census_2012.png)
![Mobility 2022](pic/mobility_census_2022.png)

#### Migration Types

![Citizenship](pic/mobility_citizenship.png)
![Foreign Born](pic/mobility_foreignborn.png)
![Migration](pic/mobility_migration.png)
![Year of Entry](pic/mobility_yearofentry.png)

#### Mobility by Race

![Mobility by Race](pic/mobility_population.png)

---

## Correlation Between Mobility and Rent Burden

### Correlation Heatmap

![Correlation Heatmap](pic/corr_heatmap.png)

Key Findings:
- Strong negative correlation between rent burden and remaining in the same house.
- Positive correlations among different types of movers.
- Higher rent burdens are linked to increased mobility.

### Scatter Plots of Mobility and Rent Burden

![Scatter Plot](pic/corr_plot.png)

---

## In-Migration Regression Results

### Regression Table (Two-Way Fixed Effects)

(*For full statistical details, see LaTeX source.*)

![Panel Regression Plot](pic/panel_regression_result.png)

- Recent immigrants correlate with higher rent burdens.
- White/Asian migration increases burden; Black migration decreases it.
- R² is low: more factors likely influence outcomes.

---

## Summary of Results

- Rent burden has declined in some areas but may reflect displacement.
- Mobility patterns show affordability pressure, especially for immigrants.
- Correlation confirms high rent burdens link to higher relocation likelihood.
- Displacement patterns reflect broader socioeconomic and racial inequality.

---

## Conclusion

The study highlights the complex relationship between rent burden and mobility:
- Decline in burden may not mean affordability has improved.
- Displacement driven by rising rent burdens is still strong.
- Policy is needed to ensure tenant protections, affordability, and community stability.

---

## Appendix

### Median Household Income Trend

![Median Household Income](pic/median_household_income.png)

### Descriptive Statistics

| Variable | Mean | SD | Min | Max |
|----------|------|----|-----|-----|
| Rent Burden | 7.42 | NA | 7.42 | 7.42 |
| Total Population | 743,668.8 | 16,093.5 | 712,040 | 759,450 |
| Same House Movers | 367,266.8 | 8,913.8 | 350,157 | 375,428 |
| Within State Movers | 376,402 | 7,581.8 | 361,883 | 384,402 |
| Different State Movers | 652,964.1 | 15,642.2 | 622,575 | 668,337 |
| Abroad Movers | 321,997.6 | 8,694.2 | 305,559 | 330,668 |

### Correlation Matrix

|                  | Rent Burden | Same House | Within State | Different State | Abroad |
|------------------|-------------|------------|---------------|------------------|--------|
| Rent Burden      | 1.000       | -0.915     | -0.748        | -0.865           | -0.917 |
| Same House       | -0.915      | 1.000      | 0.903         | 0.982            | 0.998  |
| Within State     | -0.748      | 0.903      | 1.000         | 0.967            | 0.885  |
| Different State  | -0.865      | 0.982      | 0.967         | 1.000            | 0.974  |
| Abroad           | -0.917      | 0.998      | 0.885         | 0.974            | 1.000  |

