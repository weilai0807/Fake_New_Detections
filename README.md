# Fake Chinese New Detections Using Machine Learning Approaches
## Introduction
As technology advances, the proliferation of fake news extends across diverse social media platforms and websites. Misleading information can lead individuals to make incorrect decisions and carries the potential to harm society if left unchecked. Individuals should engage in fact-checking for every piece of news they receive. However, it will be time consuming for individuals if they need to fact checking on every news without a proper system. Hence, there is a crucial need to identify an efficient solution for accurately detecting fake news.
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
A Chinese dataset named CHEF was collected from [Github](https://github.com/THU-BPM/CHEF?tab=readme-ov-file), it consists of 14 features and 8,558 rows. There are about 5,015 rows are labelled as fake news and 3,543 rows are true news in the dataset. The table below shows the variables name and the description.

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

Image below indicates the dataset consists of 14 features, including 12 features with object data type and 2 features with integer data type, and 8,558 rows of data.  

![image](https://github.com/weilai0807/Fake_New_Detections/blob/main/Image/Dataset%20information.png)

Image below indicates an imbalance in the dataset as the number of fake news is higher than true news.  

![image](https://github.com/weilai0807/Fake_New_Detections/blob/main/Image/Distribution%20of%20true%20and%20fake%20news.png)

Image below indicates the specific terms of true and fake news that frequently appear.The term that stands out in the WordCloud for fake news suggest that these terms typically accompany fake news content.  

![image](https://github.com/weilai0807/Fake_New_Detections/blob/main/Image/Wordcloud%20of%20true%20and%20fake%20news.png)


### Data Preparation
#### Data Preprocessing
Jieba, a powerful open-source Chinese text segmentation module, is used in this study for eliminating the IP addresses, stop words and punctuation from the text. Apart from that, Jieba is also employed for text tokenization. The table below shows some examples of claim after tokenization with Jieba.

| Claim                        | After tokenization                   |
| --------------------         | -----------------------------------  |
| 失业保险金不等于失业补助金。    | 失业 保险金 不 等于 失业 补助金        |
| 退休职工养老金能按时足额发放。  | 退休职工 养老金 能 按时 足额 发放      |
| 中国污水处理能力限制城市发展。  | 中国 污水处理 能力 限制 城市 发展      |

#### Feature Extraction
BoW, TF-IDF, BoW-TFIDF and Word2Vec are applied individually to the tokenized text to transform the textual data into numerical vectors.   

**Bag of Word (BoW)** captures the frequency of each word and it did not consider the grammatical order or structure of the words in the text. Every word within a document is treated as a discrete "token," and the outcome is a numerical vector that represents the frequency of each word.  

**Term Frequency-Inverse Document Frequency (TF-IDF)** is the multiplication of TF and IDF. TF will calculate the term frequency while IDF quantifies the importance of a word across the entire collection of documents. It effectively captures the significance of words in documents by considering their frequency across the entire document collection.  

**BoW-TFIDF** is a combination of BoW and TF-IDF. BoW, emphasizing the each word frequency in a document, is applied initially to tokenized text, generating a numerical vector. Subsequently, TF-IDF is applied to these numerical vectors, creating another numerical vector that not only captures word frequency but also considers the importance of words across the entire corpus. 

**Word2vec** is a word embedding technique used to capture the semantic and syntactic between the words based on their context. It utilizes 2 architectures, including Conti 0nuous Bag of Words (CBOW) and Skip Gram, the former predicts the target word based on the context words while the latter predict the context words based on the target word.


### Modeling
Upon completing the data preparation phase, the dataset undergoes a division, allocating 80% for training the set and 20% for the testing set. To optimize the performance of each machine learning model, a grid search is systematically applied, exploring various combinations of hyperparameters. Also, 5-fold cross validation has been applied in the grid search to address the challenge posed by the imbalanced dataset.  
Fake news classification will involve the utilization of 4 traditional ML models: SVM, NB, RF, and KNN. Additionally, 3 DL models, namely CNN, LSTM, and a hybrid CNN-LSTM model, will be employed in this classification task.

#### Support Vector Machine (SVM)
SVM is good in solving complex problems and handling high-dimensional data. When the dataset consists of many attributes, it may refers to high-dimensional data. Also, it is well suited for binary classification tasks. The kernel function in SVM can be changed, different kernel functions will affect the performance.

#### K-Nearest Neighbours (KNN)
The classification of KNN is based on the distance metric. For example, if there are 2 class A instances and 1 class B instance within the distance of the new instance, it will be classified as class A.  The choice of K is crucial as it will affect the models’ performance. To determine the best K value, adjusting the K value and iterating the process can help. Furthermore, it does not rely on making stringent assumptions about the distribution of the data.

#### Random Forest (RF)
It constructs an ensemble of decision trees to generate predictions. It creates diverse subsets of training data by using the bagging and feature randomness. After that, each decision tree operates on a specific subset. Each decision will then select the best feature to each node based on the criterion. The final prediction is determined by aggregating the majority votes from all decision trees. RF is capable of handling complex datasets and not prone to overfitting.

#### Naïve Bayes (NB)
To predict class of data, NB calculates the probability of the data to each class. After that, the data is assigned to the class with the highest probability. It assumes all features in the dataset are independent among each other. This implies that the presence or absence of a feature does not influence the other features in the dataset.

#### Long Short-Term Memory (LSTM)
LSTM is an advanced version of recurrent neural network (RNN) that is able to handle long-term dependencies between data point. Therefore, it does not suffer from the vanishing gradient problem faced by RNN. LSTM has the gate mechanism that determines which part of information will be needed for the next cell and which part is to be discarded. There are 3 gates, including forget gate, input gate and output gate. Forget gate removes the useless information in the cell state. The input gate decides which new information is to be stored in the cell state. Lastly, the output gate produces the final output by extracting the useful information from the current cell state. 

#### Convolutional Neural Networks (CNN)
CNN is a deep learning model that is primarily designed for processing and analyzing the data, including texts, images and videos. It is always utilized for classification and computer vision tasks. CNN comprise of 3 main types of layers, such as convolutional layer, pooling layer, fully connected (FC) layer. Convolutional layer responsible for capturing the local patterns and features. It achieves this by applying convolutional filters to the sequence of word vectors. The pooling layer reduces the dimensionality of the data while retaining important information. Lastly, the FC layer produces the output of the network.

#### CNN-LSTM
The hybrid CNN-LSTM model utilized the strengths of both Convolutional Neural Network and Long Short-Term Memory Networks. CNNs excel at capturing local patterns and spatial relationships within the input data. On the other hand, LSTMs are effective for modeling sequential dependencies and long-term relationships. 

### Evaluation
4 evaluation metrics will be employed, including accuracy, precision, recall and F1 score.

**Accuracy** is calculated by dividing the sum of TP and TN by the sum of TP, TN, FP and FN. The formula of accuracy is shown below:  

![image](https://github.com/weilai0807/Fake_New_Detections/blob/main/Image/Accuracy1.png)  

TP is True Positives, TN is True Negatives, FP is False Positives and  FN is False Negatives.

**Precision** measures how many instances are predicted as positive out of all instances that are predicted as positive. The formula is shown below:  

![image](https://github.com/weilai0807/Fake_New_Detections/blob/main/Image/Precision.png)

**Recall** measure how many instances are predicted as positive out of all positive instances. The formula is shown below:  

![image](https://github.com/weilai0807/Fake_New_Detections/blob/main/Image/Recall.png)

**F1-score** is calculated with both precision and recall value, so it provides a more balanced value. The formula is shown below: 

![image](https://github.com/weilai0807/Fake_New_Detections/blob/main/Image/F1-Score.png)

### Deployment
After determining the optimal model, the next step involves deploying it using Streamlit, a Python-based open-source application framework. Initially, the model is saved as a SAV file, and subsequently, it is loaded into the Spyder (anaconda3) for data product deployments. Apart from model loading, this phase also involves designing the interface of the web application to ensure simplicity and user-friendliness. After that, it is deployed on the Streamlit Community Cloud, making it accessible to the public.

## Results and Discussion
### Performance of all models on fake new classifications
![image](https://github.com/weilai0807/Fake_New_Detections/blob/main/Image/4.3%20Result%201.png)  

Table above presents the results of 4 traditional ML algorithms and 3 DL algorithms with 5 feature extraction techniques. Image illustrates that the traditional ML model exhibiting the highest performance is SVM with BoW-TFIDF, achieving an accuracy of 86.04%. On the other hand, the deep learning model with the best performance is CNN with Baselines, achieving an accuracy of 84.40%. Several factors contribute to this discrepancy. DL models exhibit lower performance compared to traditional ML models because DL models may require more data to train, but the dataset employed in this study is relatively small. Furthermore, finding the optimal hyperparameter for deep learning could be challenging as deep learning models often involve a large number of hyperparameters. Besides, traditional machine learning models often excel in simpler tasks, whereas the increased complexity of deep learning models makes them more suitable for complex tasks.  

In conclusion, the superior performance of SVM with BoW-TFIDF among traditional ML models performs better than the DL models, CNN with baselines in this study due to the reason mentioned above.  

![image](https://github.com/weilai0807/Fake_New_Detections/blob/main/Image/4.3%20Result%202.png)

### Fake news detection web application
The SVM model with BoW-TFIDF has been chosen for the development of the data product as it achieved the highest accuracy rate of 86.04%. The fake new detection web application can be accessed through the following link: [Fake News Detection Web App](https://fakenewsdetectionapp.streamlit.app/).  


## Conclusion
### Achievements
The result of this study has successfully addressed the Research Question (RQ) and Research Objective (RO) outlined in [Introduction](##Introduction). The application of 5 feature extraction techniques revealed that BoW-TFIDF stands out as the best method for enhancing the ML algorithms performance. A comprehensive comparison involving feature extraction techniques and ML algorithms was done to identify the most effective pairing. Lastly, evaluation metrics such as accuracy, precision, recall and F1-score are used to measure the performance of ML models.
Based on the result in Chapter 4, SVM with BoW-TFIDF is the best model that can accurately detect fake news. It also been deployed on the Streamlit Community Cloud for public accessibility.

