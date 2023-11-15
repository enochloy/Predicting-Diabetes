# Predicting Diabetes

### Objectives

* Using the NHANES glycohemoglobin dataset, the project aims to predict patients with glycohemoglobin >= 6.5% using several risk factors such as sex, age, income levels amongst others.

---

### Data Dictionary

`nhgh.tsv`


| Feature   | Type     | Description                                      |
|-----------|----------|--------------------------------------------------|
| seqn      | numeric  | Respondent sequence number                       |
| sex       | string   | Gender                                           |
| age       | numeric  | Age in years                                     |
| re        | string   | Race/Ethnicity                                   |
| income    | string   | Family Income                                    |
| tx        | numeric  | On Insulin or Diabetes Meds                      |
| dx        | numeric  | Diagnosed with DM or Pre-DM                      |
| wt        | numeric  | Weight in kg                                     |
| ht        | numeric  | Standing Height in cm                            |
| bmi       | numeric  | Body Mass Index (kg/m^2)                         |
| leg       | numeric  | Upper Leg Length in cm                           |
| arml      | numeric  | Upper Arm Length in cm                           |
| armc      | numeric  | Arm Circumference in cm                          |
| waist     | numeric  | Waist Circumference in cm                        |
| tri       | numeric  | Triceps Skinfold in mm                           |
| sub       | numeric  | Subscapular Skinfold in mm                       |
| gh        | numeric  | Glycohemoglobin (%)                              |
| albumin   | numeric  | Albumin in g/dL                                  |
| bun       | integer  | Blood urea nitrogen in mg/dL                     |
| SCr       | numeric  | Creatinine in mg/dL                              |


<br>

---




### Results


| Model                     | Train Recall Score | Test Recall Score |
|---------------------------|--------------------|-------------------|
| Logistic Regression       | 0.83               | 0.87              |
| Random Forest Classifier  | 0.86               | 0.87              |
| Decision Tree Classifier  | 0.84               | 0.82              |

- I chose to optimize recall as we want to minimize false negatives (predicting no diabetes when the patient has diabetes).
- Random Forest Classifier seems to have the best performance based on train/test recall scores.
- I dropped many co-linear variables with no significant impact on the model's performance.
    - Weight
    - Height
    - Arm circumference
    - BMI
    - Tricep thickness
    - Subscapular thickness
    - Serum Creatinine
    - Blood urea nitrogen
    - Upper bound income
    - Treatment