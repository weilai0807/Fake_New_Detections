# Fake New Detections Using Machine Learning Approaches
## Abstract
Driven by technological advancements, fake news has significantly grown year over year especially propagated through social media platforms. It carries many potential harms that plagued society for so many years and necessitates urgent attention. This study proposes the best model that can detect Chinese fake news accurately by conducting a comprehensive analysis of feature extraction, machine learning and deep learning algorithms. The methodology of this research, encompassing phases like Data Understanding, Data Preparation, Modeling, Evaluation and Deployment, was carried out to address research questions and achieve research objectives. The CHEF dataset consists of data from many domains, including politics, science, public health and more is used for model training in this study. The result from this study concludes that BoW-TFIDF as a feature extraction technique performs well across all machine learning algorithms. BoW-TFIDF utilizes the strengths of both BoW and TFIDF, with BoW counting the word frequency and TFIDF captured the significance of word throughout the entire corpus. The comparative analysis of model performance revealed that SVM with BoW-TFIDF is the bestmodel in detecting Chinese Fake News. It obtained the greatest scores in accuracy (86.04%), precision (87.88%), and F1-score (88.75%). Subsequently, SVM with BoW-TFIDF was deployed on Streamlit Community Cloud for public accessibility. This study not only emphasizes the importance of fake news detection but also identify the most effective model through a well-structured methodology.

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

## Literature Review
You may refer to the research paper for this section. [Link]("https://miro.medium.com/max/1024/1*mwXHpdt6CTQHxH78dwc6NA.jpeg")
## Methodology

## Results and Discussion

## Conclusion

Fake new detection web application: https://fakenewsdetectionapp.streamlit.app/
