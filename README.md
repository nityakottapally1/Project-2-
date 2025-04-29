# Leading Causes of Death: United States 

## Group 2
1. Alicia Jarvis - [aliciajarvis-ai](https://github.com/aliciajarvis-ai)
2. Oliver Schouest - [oschouest](https://github.com/oschouest)
3. Tejas Panicker - [Tejas5012](https://github.com/Tejas5012)
4. Nitya Kottapally - [nityakottapally1](https://github.com/nityakottapally1)
5. Aman Sathani - [amansathani](https://github.com/amansathani)
---
## Why We Picked this Database 
We explored the "NCHS - Leading Causes of Death: United States" data set to understand mortality trends across the country. The data set was obtained from Data.gov, provided by the CDC's National Center for Health Statistics (NCHS) via the National Vital Statistics System. It combines information from resident death certificates in all 50 states and the District of Columbia from 1999 to 2017 and conforms to ICD-10 criteria for cause-of-death coding.

This data enables us to call attention to significant health issues, including Heart disease and Cancer, and enables data-driven decision-making through uncovering mortality trends. Our aim was to develop an interactive Tableau dashboard that visualizes these trends so that insights such as the leading causes of death in 2017 would be more accessible. With a total of almost 113,000 records spanning 19 years, the data offers a strong basis for exploring U.S. mortality trends.

---
## Data Set Columns

| Column Name              | Data Type | Description                                                                                       |
|--------------------------|-----------|---------------------------------------------------------------------------------------------------|
| Year                     | Integer   | The year of the data observation (e.g., 2017).                                                    |
| 113 Cause Name           | String    | Detailed classification of the cause of death (e.g., "Diseases of heart (I00-I09,I11,I13,I20-I51)"). |
| Cause Name               | String    | Simplified cause of death (e.g., "Heart disease").                                                |
| State                    | String    | Geographic location, either a U.S. state or "United States" (e.g., "Alabama").                    |
| Deaths                   | Integer   | Raw number of deaths for the cause in that state and year (e.g., 12345).                          |
| Age-adjusted Death Rate | Float     | Death rate per 100,000 population, adjusted for age distribution (e.g., 277.1).                   |

### Notes
- The data set has 6,864 rows and 6 columns, thus making it a rich but not overwhelming data set for analysis. Every row corresponds to a particular cause of death in a particular state and year, while the columns offer precise metrics. 
- The dataset is sourced from the National Center for Health Statistics (NCHS) and covers leading causes of death in the U.S. from 1999 to 2017.
- This dataset was used to analyze age-adjusted death rates for Heart disease in 2017, comparing northern and southern U.S. states.


---
## Question 1
**What is the overall trend in age-adjusted death rates for Heart Disease by state from 1999 to 2017, and how does this trend vary regionally across the U.S.?**

### Model 
![image](https://github.com/user-attachments/assets/a703caa2-a910-4a02-9f63-d5aa8f835169)
---
### Importance 
Heart disease has been a leading cause of death in the U.S. for decades, contributing to significant morbidity and mortality. Understanding how death rates have changed over time can reveal the effectiveness of public health interventions, such as smoking cessation programs, improved access to healthcare, and advancements in cardiovascular treatments. States with the largest decreases may serve as models for successful interventions.

Lifestyle factors like diet, exercise, and smoking vary culturally across states. For example, southern states (e.g., Mississippi) often have higher rates due to cultural dietary habits (e.g., high-fat diets). Understanding changes can shed light on how cultural shifts or interventions have impacted health outcomes.

---

### Manipulations

We generated heat maps for 1999 and 2017 using the following filters:

- **Cause Name**: Filtered for `"Heart Disease"` (the leading cause with the highest age-adjusted death rate)
- **Year**: Filtered for 1999 and 2017
- **State**: Removed entries for `"United States"` to focus on individual state comparisons

This allowed us to compare state-level trends across the two years.

---

### Analysis

The heat maps reveal a clear trend:  

- In **1999**, most states appeared in darker blue, indicating **higher death rates**  
- By **2017**, many states shifted toward lighter shades, suggesting a **general decrease** in heart disease mortality  

**Example:**  
- **Mississippi** had the highest age-adjusted death rate in 1999 at **347.4**  
- By 2017, this dropped significantly to **237.2**, showing progress though still among the highest in the nation

While both the graphs showed a overall decrease in Adjusted Death rates, due to increased access to healthcare (such as vaccines, national health awareness campaigns), however by 
analyzing these specific grpahs we can examine whether certain states exhibited signifcant changes allowing for us to theroize and examine their actiosn taken towards decreasing heart disease related deaths. 
This consistent decline reflects both medical progress and targeted public health efforts, although regional disparities remain evident.

---
