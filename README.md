# Success-Prediction-Analysis-for-Startups
## Introduction
Startups are companies started by an individual or a small group of people based on a unique business idea. Most of the startups face high failure rates whereas few startups are very successful such as Facebook, Uber, and Snapchat etc. On average 90% of startups fail to succeed in their respective field of business. This work proposes a predictive method to determine the outcome of start-ups based on several key factors that contribute to the success such as Acquisitions, Investments, Total rounds of funding etc.  The analysis is done using various techniques such as ***Logistic Regression, Principal Component Analysis, Decision Trees, Gradient Boosted Trees, Random Forest and Neural Network***. The proposed models are evaluated based on factors such as accuracy and area under ROC curve. A start-up company can make use of the proposed analysis to determine the important factors and areas that are needed to be focused and improved to have a successful venture. </br>

## Startups - IPO and M&As
The success of a startup is generally categorized as a two-way strategy. One, a company can have an *IPO (Initial Public Offering)* in which the company goes to a public share market where shareholders have the right to sell the share to the public. Other is being *Merged or Acquired (M&A)* by other company where the shareholders or the people who invested in the startup receive cash in return for their shares immediately. This is often referred to as the exit strategy. </br>

## Methodology

The primary aim of this research is to develop a success prediction models for startup using acquisition information by which a company can make use of the proposed analysis to determine the important factors and areas that are needed to be focused and improved to have a successful venture also to predict the probability of the startup to be acquired. Data Mining methods are used in this project to make insightful decisions using the data collected from the sources which will result in effective outcomes. </br>

### Data Collection
The data is obtained from ***CrunchBase*** website using API.  CrunchBase is a website which has information about public and private companies around the world. These information includes funding and investment details, details of founding members and individuals in leadership positions, information about acquisitions, mergers, latest trends and news. The dataset consists of details of various start-up companies from all over the world. These details include start date, start location, seed funding, total rounds of funding, valuation, market value, investment and acquisition details etc. Regardless of being community based, for small to medium companies, CrunchBase acts as an important resource for various venture capitals, consulting, marketing and sales companies as well as for academic research studies. This website acts as a database for reference of all startup and investor information. </br>

### Data Cleaning and Pre-processing
Cleaning the data is one of the foremost steps in the process of this research project. Data cleaning plays a key role in deriving the output of a machine learning model. Usually data cleaning consists of processes like determining outliers and removing or imputing outliers, removing or replacing missing values, removing duplicate values, removing values with less or no importance. </br>
*Data Visualisation* plays an important role in understanding the data as it gives an overview of the data before the modelling process. *Exploratory Data Analysis (EDA)* is a method of analysing the data and summarizing the outcomes or insights using visual techniques. EDA is used for initial investigation of the data to produce useful outcomes and visual representations which can be helpful in learning the data before building Machine Learning algorithms. The patterns and anomalies can be discovered by doing EDA also assumptions can be checked and hypothesis can be tested. In this work Exploratory Data Analysis is done using Tableau. </br>

## Modelling
In this phase, the selection of proper modelling technique with respect to the prepared data is done. The dataset is divided into sub-groups and processed using multiple modelling methods which can result in effective outcomes. It is one of the crucial phase because choosing of appropriate model can affect the outcome of the project. </br>
Before building model, the dataset transformed into CSV file from the data cleaning and preparation step is imported into a spark dataframe. This data is further cleaned by removing columns with too many levels and inconsistent data and the missing values are also removed. Data is prepared by creating index for categorical variables and converting string to double for numerical variables. The data is split into training, testing and validation sets in the following ratio: </br>

| dataframe name | split percentage |
| -------------- | ---------------- |
| training_df    | 60%              |
| validation_df  | 30%              |
| testing_df     | 10%              |

After splitting the data, the vector assembler is defined with features for modelling. Vector Assembler is used to merge the raw features and features generated from various attributes into a single feature vector. It is generally used to merge all the available features before building a model. </br>
The models are used in this project to check for maximum efficiency. They are,
- Decision Tree
- Gradient Boosted Trees
- Random Forest
- Logistic Regression
- Principal Component Analysis (PCA)
- Multilayered Perceptron Neural Network

## Model Evaluation
Before the derivation of the outcomes of the model and conclusion of the project, the model has to be evaluated and reviewed based on the outcome with respect to the objective of the project work and it is carried out in this phase. The success rate of the project can be validated in this phase and it can be used for future processing. </br>
In this project two evaluation methods are used to evaluate the models built. They are ***Binary Classification Evaluator*** and ***Multiclass Classification Evaluator***. </br>

## Results

![Number of companies acquired vs Acquirer name](https://github.com/yogeshwaran-shanmuganathan/Success-Prediction-Analysis-for-Startups/blob/main/Result_Visualization_Images/Number%20of%20companies%20acquired%20vs%20Acquirer%20name.png)

The above image represents the maximum number of companies acquired by a single acquirer. Since this project is based on the acquisition data and the main objective is to provide predictions or probabilities on whether the startup company might get acquired, this visualisation is an important result of this research project. It can be seen that Cisco has acquired the maximum number of company than any other company. With 168 companies acquired, Cisco ranks first and with a slight less number of 165 companies acquired Google stand next to Cisco. </br>

![Types of funds received by the companies](https://github.com/yogeshwaran-shanmuganathan/Success-Prediction-Analysis-for-Startups/blob/main/Result_Visualization_Images/Types%20of%20funds%20received%20by%20the%20companies.png)

The above image illustrates the types of funding received by companies. Most of the companies receive funds as venture from venture capitals. </br>

![Distribution of Target Variable](https://github.com/yogeshwaran-shanmuganathan/Success-Prediction-Analysis-for-Startups/blob/main/Result_Visualization_Images/Distribution%20of%20Target%20Variable.png)

Above image represents the distribution of target variable. In this project, the target variable is an indication of the acquisition status of the company. It has two values – 0 indicates that the company is not acquired and 1 indicates that the company is acquired. </br>

![Accuracy of Models](https://github.com/yogeshwaran-shanmuganathan/Success-Prediction-Analysis-for-Startups/blob/main/Result_Visualization_Images/Accuracy%20of%20Models.png)

It can be seen from the above image that the accuracy of Logistic Regression is higher than the other models. But there is not much difference between the accuracy percentages of other models and Logistic Regression model. </br>

![Area under ROC Curve of models](https://github.com/yogeshwaran-shanmuganathan/Success-Prediction-Analysis-for-Startups/blob/main/Result_Visualization_Images/Area%20under%20ROC%20Curve%20of%20models.png)

From the above image, it can be seen that the AUC value of Multilayer Perceptron Neural Network is higher when compared to other models. Though Random Forest and Logistic Regression with PCA algorithms have higher accuracy they have significantly low AUC values. Neural networks perform the best overall with a huge increase in the AUC value and also a better accuracy in comparison to the other models. </br>

## Conclusion
From the results, it can be concluded that Multilayer Neural Network with 3 hidden layers with 30 neurons each performs the better as it has the overall best Area under Curve (AUC) and better accuracy when compared to other models. It would be really worth it to increase those numbers of Neural Network further with the optimal number of hidden layers and neurons and also with a more powerful machine with better processing speeds and memory. </br>

###### Note: This applied project is done as a part of my final dissertation or applied project for the completion of Master of Science in Data Analytics at Dublin Business School, Dublin, Ireland.
