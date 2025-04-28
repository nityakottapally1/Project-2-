# Leading Causes of Death: United States 

## Group 2
1. Alicia Jarvis - [aliciajarvis-ai](https://github.com/aliciajarvis-ai)
2. Oliver Schouest - [oschouest](https://github.com/oschouest)
3. Tejas Panicker - [Tejas5012](https://github.com/Tejas5012)
4. Nitya Kottapally - [nityakottapally1](https://github.com/nityakottapally1)
5. Aman Sathani - [amansathani](https://github.com/amansathani)

## Data Base Description 
We explored the "NCHS - Leading Causes of Death: United States" data set to understand mortality trends across the country. The data set was obtained from Data.gov, provided by the CDC's National Center for Health Statistics (NCHS) via the National Vital Statistics System. It combines information from resident death certificates in all 50 states and the District of Columbia from 1999 to 2017 and conforms to ICD-10 criteria for cause-of-death coding.

The data set has 6,864 rows and 6 columns, thus making it a rich but not overwhelming data set for analysis. Every row corresponds to a particular cause of death in a particular state and year, while the columns offer precise metrics. Columns are: Year (integer, e.g., 2017, data year); 113 Cause Name (string, e.g., "Malignant neoplasms (C00-C97)," specific cause with ICD-10 coding); Cause Name (string, e.g., "Cancer," a general cause category); State (string, e.g., "Mississippi" or "United States" for national values); Deaths (integer, e.g., 5,000, number of deaths due to that cause); and Age-adjusted Death Rate (float, e.g., 165.0, death rate per 100,000 population, adjusted using the 2000 and 2010 U.S. census data to make equitable comparisons across populations and over time).

This data enables us to call attention to significant health issues, including Heart disease and Cancer, and enables data-driven decision-making through uncovering mortality trends. Our aim was to develop an interactive Tableau dashboard that visualizes these trends so that insights such as the leading causes of death in 2017 would be more accessible. With a total of almost 113,000 records spanning 19 years, the data offers a strong basis for exploring U.S. mortality trends.

## Question 1
What is the overall trend in age-adjusted death rates for Heart disease by state from 1999 to 2017, and how does this trend vary regionally across the U.S.?

### Model 
![image](https://github.com/user-attachments/assets/a703caa2-a910-4a02-9f63-d5aa8f835169)

### Importance 
Heart disease has been a leading cause of death in the U.S. for decades, contributing to significant morbidity and mortality. Understanding how death rates have changed over time can reveal the effectiveness of public health interventions, such as smoking cessation programs, improved access to healthcare, and advancements in cardiovascular treatments. States with the largest decreases may serve as models for successful interventions.

Lifestyle factors like diet, exercise, and smoking vary culturally across states. For example, southern states (e.g., Mississippi) often have higher rates due to cultural dietary habits (e.g., high-fat diets). Understanding changes can shed light on how cultural shifts or interventions have impacted health outcomes.

### Manipulations 

### Analysis 
The heat map shown displayes a clear trend, in 1999 most states lie closer to blue whilst in 2017 most states have shifted towards red indicating a general decrease in heart disease rates over this 18 year period. 

In 1999 Missisipi had the highest adjusted death rate at 347.4 however in 2017 that number had sunk down to 237.2. Similarly 
