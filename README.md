# Leading Causes of Death: United States 

## Group 2
1. Alicia Jarvis - [aliciajarvis-ai](https://github.com/aliciajarvis-ai)
2. Oliver Schouest - [oschouest](https://github.com/oschouest)
3. Tejas Panicker - [Tejas5012](https://github.com/Tejas5012)
4. Nitya Kottapally - [nityakottapally1](https://github.com/nityakottapally1)
5. Aman Sathani - [amansathani](https://github.com/amansathani)
---
## Why We Picked This Database

We selected the **"NCHS - Leading Causes of Death: United States"** dataset to explore mortality trends across the U.S. The dataset was sourced from [Data.gov](https://data.gov) and provided by the CDC’s **National Center for Health Statistics (NCHS)** via the **National Vital Statistics System**.

This dataset aggregates information from resident death certificates across all 50 states and the District of Columbia, covering the years **1999 to 2017**. It adheres to **ICD-10** criteria for cause-of-death classification, ensuring consistent and standardized reporting.

Our decision was guided by the following motivations:

- To **highlight major health concerns** such as heart disease and cancer.
- To **enable data-driven analysis** by uncovering mortality trends over time.
- To **create an interactive Tableau dashboard** that helps visualize key insights, such as the leading causes of death in 2017.

With nearly **113,000 records spanning 19 years**, this dataset offers a robust foundation for understanding how causes of death have evolved nationwide. Ultimately, our goal was to make these insights more accessible and actionable for public health discussions and decision-making.


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
- This dataset was used to analyze age-adjusted death rates for Heart disease in 2017, comparing northern and southern U.S. states.


---
## Question 1
**What is the overall trend in age-adjusted death rates for Heart Disease by state from 1999 to 2017, and how does this trend vary regionally across the U.S.?**

---
### Model 
![image](https://github.com/user-attachments/assets/a703caa2-a910-4a02-9f63-d5aa8f835169)
---
### Importance 
Heart disease has been a leading cause of death in the U.S. for decades, contributing to significant morbidity and mortality. Understanding how death rates have changed over time can reveal the effectiveness of public health interventions, such as smoking cessation programs, improved access to healthcare, and advancements in cardiovascular treatments. States with the largest decreases may serve as models for successful interventions.

Lifestyle factors like diet, exercise, and smoking vary culturally across states. For example, southern states (e.g., Mississippi) often have higher rates due to cultural dietary habits (e.g., high-fat diets). Understanding changes can shed light on how cultural shifts or interventions have impacted health outcomes.

---

### Manipulations

We generated heat maps for 1999 and 2017 using the following filters:

- **Cause Name**: Filtered for `"Heart Disease"` (the leading cause with the highest age-adjusted death rate). Also used in Marks, to set a blue to red color scheme. 
- **Year**: Filtered for 1999 and 2017
- **State**: Removed entries for `"United States"` to focus on individual state comparisons. Also used in Marks, to set up the heat map by state. 


This allowed us to compare state-level trends across the two years.

---



### Analysis

The heat maps reveal a clear trend:  


- In **1999**, most states appeared in darker blue, indicating **higher death rates**  
- By **2017**, many states shifted toward red, suggesting a **general decrease** in heart disease mortality  
- Despite overall decline, **southern states still show elevated rates**, indicating persistent regional disparities likely tied to diet, poverty, and healthcare access.


While both the graphs showed a overall decrease in Adjusted Death rates, due to increased access to healthcare (such as vaccines, national health awareness campaigns), however by 
analyzing these specific graphs  we can examine whether certain regions exhibited larger levels of heart disease related deaths allowing for further examination of the root causes. Such as the impact of diet, poverty, and other factors.  

---

## Question 2
**Is there a statistically significant correlation between death rates from diabetes and heart disease across states with the highest mortality for each?**

---
### Model
![image](https://github.com/user-attachments/assets/6dbdf8fe-acf5-4607-a95f-1c0728aaf8db)
---

### Importance

Understanding the correlation between death rates from **diabetes** and **heart disease** across states with the highest mortality is crucial for several reasons:

- **Shared Risk Factors**: Both diseases are influenced by similar health behaviors and conditions, such as poor diet, obesity, lack of physical activity, smoking, and high blood pressure.
- **Strategic Public Health Planning**: A strong correlation supports designing unified public health interventions that target both conditions at once, making programs more efficient and impactful.
- **Resource Allocation**: Identifying correlations can guide public health officials to invest resources where they’re most needed and avoid redundant disease-specific strategies.
- **Addressing Regional Disparities**: Correlated mortality patterns may reflect underlying systemic issues (e.g., access to healthcare, income inequality) in specific regions, especially in the Southern U.S.
- **Predictive Insights**: If diabetes mortality is strongly correlated with heart disease mortality, it could act as an early indicator for regions at high cardiovascular risk, supporting proactive intervention.


---

### Manipulations
#### Calculated Fields 
| **Calculated Field Name**       | **Equation**                                                                 | **Explanation**                                                                                         |
|----------------------------------|------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| Average Diabetes Rate            | `IF [Cause Name] = "Diabetes" THEN [Age-adjusted Death Rate] END`           | Filters records to include only those with "Diabetes" as the cause, then returns the corresponding age-adjusted death rate. Used to calculate the average diabetes mortality rate. |
| Average Heart Disease Rate       | `IF [Cause Name] = "Heart disease" THEN [Age-adjusted Death Rate] END`      | Filters records to include only those with "Heart disease" as the cause, then returns the corresponding age-adjusted death rate. Used to calculate the average heart disease mortality rate. |

To analyze the state-level mortality patterns for diabetes and heart disease across the US, we created a scatter plot to convey our information. 
- **Measures used:** We used the average Diabetes Rate (calculated field that filters the cause to diabetes and then has the age adjusted death rate included)  as the X-axis and the average Heart Disease Rate (calculated field that filters the cause to heart disease and then has the age adjusted death rate included) 
- **State-Level Focus:** We filtered out the “United States” entity to ensure that each data point represents a state/territory.
- **Marks:** We added State to the Color mark to make it obvious that there were multiple states involved and easily identifiable as they are all different colors. 
- **Trend Line:** We added a linear regression trend line from the analytics panel to evaluate the correlation between the two death rates. 
- **Filter Options:** Earlier to developing the final sheet, we used Cause Name and Year filters to isolate the specific causes we were looking at to ensure we had relevant and consistent data. 

---

### Analysis
The scatter plot demonstrates a strong positive correlation between average diabetes death rates and average heart disease death rates across U.S. states.
States with a **higher diabetes mortality** tend to also experience **elevated heart disease mortality**, suggesting overlapping health risk factors. The linear trend line reinforces the statistical relationship, with most data points clustering near the line, indicating consistency in the pattern.

This correlation may be driven by shared contributors such as:

- Poor diet and nutrition
- Obesity
- Lack of access to preventative healthcare
- Socioeconomic and cultural factors, especially in Southern and rural states

The visual makes it clear that targeting diabetes prevention and management could also lower heart disease mortality. This supports the importance of holistic chronic disease prevention strategies at the state level.

---

## Key Insights

- Our first question led us to understand that Heart disease death rates have **decreased significantly** from 1999 to 2017 across most states.
- **Southern states** continue to lag, with higher mortality rates than the national average.
- A **positive correlation** exists between diabetes and heart disease death rates, emphasizing the need for coordinated public health efforts.

---

### Tableau Package 

We have attached both the Graphs to the repository. 

---

## References
Centers for Disease Control and Prevention. (2022). *NCHS - Leading Causes of Death: United States*. [Data.gov](https://catalog.data.gov/dataset/nchs-leading-causes-of-death-united-states)



