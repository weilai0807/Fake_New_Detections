# Fake New Detections Using Machine Learning Approaches
## Introduction
As technology advances, the proliferation of fake news extends across diverse social media platforms and websites. Misleading information can lead individuals to make incorrect decisions and carries the potential to harm society if left unchecked. Individuals should engage in fact-checking for every piece of news they receive. However, it will be timeconsuming for individuals if they need to fact checking on every news without a proper system. Hence, there is a crucial need to identify an efficient solution for accurately detecting fake news.
### Research Questions (RQ)
**RQ1**: What are the most effective feature extraction techniques to ensure detection accuracy?  
**RQ2**: How to improve machine learning models through hyperparameter tuning to accurately detect the fake news?  
**RQ3**: Which machine learning models are the most accurate in detecting fake news?  
### Research Objectives (RO)
**RO1**: To explore the effectiveness of different feature extraction techniques in enhancing fake news detection model performance.  
**RO2**: To propose machine learning models capable of accurately detecting fake news.  
**RO3**: To evaluate proposed machine learning models using appropriate evaluation metrics.  

## Methodology
A well-structured methodology was employed for detecting fake news.  

![Screenshot](https://github.com/weilai0807/Fake_New_Detections/blob/main/Image/Methodology.png)

### Data Understanding
A Chinese dataset named CHEF was collected from [Github](https://github.com/THU-BPM/CHEF?tab=readme-ov-file), it consists of 14 features and 8,558 rows. There are about 5,015 rows are labelled as fake news and 3,543 rows are true news in the dataset. 

| Variables            | Description                                                      |
| -------------------- | ---------------------------------------------------------------- |
| Claim                | Statement being made                                             |
| Title                | Title of the fact-checking news                                  |
| Source               | Source of claim                                                  |
| ClaimWeb             | Website of fact-checking news                                    |
| Category             | Category of fact-checking news                                   |
| Url                  | Uniform Resource Locator (URL) of fact-checking news             |
| Publish_date         | Publish Date of fact-checking news                               |
| Editor               | Editor of fact-checking news                                     |
| Label                | Label of claim; 0 = true, 1 = fake                               |
| ClaimId              | ID of claim                                                      |
| Domain               | Domain of claim                                                  |
| Verification method  | Method used to verify the authenticity of claim                  |
| Evidence             | Supporting evidence for evaluation or verification of claim      |
| Gold evidence        | Crucial short evidence for evaluation or verification of claim.  |

#### Exploratory Data Analysis (EDA)
A basic EDA was conducted to gain a deeper understanding of the dataset.

![image](https://github.com/user-attachments/assets/46d95ac5-d60a-47f8-a797-92643e63d424)




### Data Preparation
### Modeling
### Evaluation





## Results and Discussion

## Conclusion

Fake new detection web application: https://fakenewsdetectionapp.streamlit.app/
