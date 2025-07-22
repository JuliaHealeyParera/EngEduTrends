# Educational Outcome of English Students

## Project Overview: 
This project investigates which longitudinal factors best predict educational attainment (measured by average highest qualification achieved by age 22) among young people in towns across England. Using a dataset from the UK Office for National Statistics via TidyTuesday, we develop a linear regression model to identify key predictors of educational achievement.

## Research Question:
Which factors measured over time are significantly associated with educational attainment by age 22 for students in the 2012 Key Stage 4 cohort in England?

## Data Description
- **Source**: UK Office for National Statistics via [TidyTuesday (2024-01-23)](https://github.com/rfordatascience/tidytuesday/blob/master/data/2024/2024-01-23/readme.md)
- **Observations**: 1,104 towns in England
- **Target Variable**:  
  - `highest_level_qualification_achieved_b_age_22_average_score` — average of highest qualification scores in each town
- **Key Predictors**:
  - `rgn11nm_combined`: UK region (South, North East, North West, Other)
  - `level4qual_residents35_64_2011`: Educational level of adult residents (categorized)
  - `level_3_at_age_18`: % of students earning Level 3 qualifications by age 18
  - `activity_at_age_19_full_time_higher_education`: % of cohort in full-time higher education at 19
  - `key_stage_4_attainment_school_year_2012_to_2013`: % of students earning A–C grades on GCSEs
- **Interaction Term**:
  - `level4qual_residents35_64_2011 * level_3_at_age_18`
    
##  Methodology
- Built a multiple linear regression model using statistically significant predictors
- Combined UK regions for better model fit and interpretability
- Verified assumptions: linearity, homoscedasticity, multicollinearity, normality, independence
- **Adjusted R²** > 0.92
- Breusch-Pagan test indicated minor heteroscedasticity, but residuals showed a reasonable fit

## Key Findings
- **Location Matters**: Towns in the North East and North West show higher average qualification levels than towns in the South
- **Student Performance**: Higher Level 3 qualifications and GCSE scores correlate with higher future attainment
- **Unexpected Result**: Towns with lower adult education saw higher student outcomes, possibly due to targeted interventions
- **Interaction Effect**: The benefit of student achievement is amplified in areas with highly educated adults

## Limitations
- Final location of survey participants may not reflect where they were educated
- Regional grouping ("Other") increases statistical power but loses specificity
- Model is UK-specific and may not generalize to other education systems

## Future Work
- Analyze college performance outcomes to evaluate early preparation
- Include variables like income, school funding, teacher-student ratios, and poverty rate
- Study rural vs. urban trends more closely
- Explore classification models (e.g., multinomial regression) for town/region prediction
