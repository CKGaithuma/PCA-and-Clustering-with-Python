<h1 style="text-align:center;">PCA-and-Clustering-with-Python</h1>
<div style="text-align:center;">
  <img src="images/pcaSteps.jpeg" alt="PCA Steps">
</div>

<h1 style="text-align:center;">PRINCIPAL COMPONENT ANALYSIS (PCA)</h1>
The essence of PCA is to find the directions of maximum variance in high dimensional data, and project it into
a smaller dimensional space while still retaining most of the information.

<h1 style="text-align:center;">STEPS TO IMPLEMENT PCA</h1>
* Standardize the data
* Center the data; subtract from mean.
* Calculate covariance matrix and eigenvectors.
* Project the Principal Components in the direction of the eigenvectors


<h1 style="text-align:center;">DATA UNDERSTANDING</h1>
The mpg/mtcars dataset shall be used to demonstrate PCA. The dataset originates from Seaborn, a Python library, which comes with a number of built-in datasets. The mpg dataset contains 398 entries with 9 columns. These columns contain various attributes and characteristics of different vehicle models, such as their fuel efficiency, engine specifications, weight, acceleration, manufacturing year, origin, and model name. 

Here is a breakdown of the columns:

1. mpg: Miles per gallon (fuel efficiency of the vehicle). It represents the number of miles the vehicle can travel per gallon of fuel.

2. cylinders: Number of cylinders in the engine. It indicates the number of internal combustion chambers where the air-fuel mixture is burned.

3. displacement: Engine displacement in cubic inches (cu in). It measures the total volume of all the cylinders in the engine.

4. horsepower: Engine horsepower. It represents the power output of the engine.

5. weight: Vehicle weight in pounds (lbs). It indicates the mass of the vehicle.

6. acceleration: Acceleration of the vehicle in seconds from 0 to 60 miles per hour (mph). It measures how quickly the vehicle can increase its speed.

7. model_year: Model year of the vehicle. It represents the year when the vehicle model was manufactured.

8. origin: Origin of the vehicle. It represents the manufacturing region or country of the vehicle.

9. name: Name of the vehicle model. It specifies the model or brand name of the vehicle.

<h1 style="text-align:center;">DATA PREPARATION</h1>
This Exploratory Data Analysis on the mpg dataset to check for useful insights and understanding.

- Data Visualization: Visualizations such as histograms and bar charts are useful to be able to understand the distribution and relationships between different variables in the SyriaTel dataset.

<div style="text-align:center;">
  <img src="Images/Distribution of Churn in SyriaTel.png" alt="Distribution of Churn" width="500" height="400">
</div>

- Correlation Analysis was used as a Feature Importance/Selection techinique to select the most influential features in predicting 'churn'.

- Data Preprocessing was employed to create Graphs and Visualization used to analyse data to be used for Modeling. 

<div style="text-align:center;">
  <img src="Images/Distribution of features in SyriaTel Data.png" alt="Distribution of Features">
</div>

<h1 style="text-align:center;">MODELING</h1>

The data was split into the training and test datasets. The training dataset served as the foundation for model training endeavors to fit the models. The test subset functioned as an independent validation mechanism to assess the models' predictive capabilities. A Baseline Logistic Regression Model was developed. More-complex models such as Random Forest Model, XGBoost Model and a Tuned Random Forest Model
were developed.

<h1 style="text-align:center;">EVALUATION</h1>

 Among the models evaluated, XGBoost demonstrates superior performance in terms of accuracy, precision, recall, F1 score, and ROC AUC score.
 XGBoost Model achieved an accuracy of 96.4%, a precision of 95.3%. The XGBoost Model also has the best overall performance in terms of churn prediction i.e True positives (TP). It has the highest number of true positives (81) and true negatives (562) with relatively low false positives (4) and false negatives (20).
 Evaluating the Models based on the ROC AUC (Receiver Operating Characteristic - Area Under the Curve) metric:

 - The Baseline Model using Logistic Regression achieved an ROC AUC score of 0.8760. This indicates that the model performs reasonably well in distinguishing between the positive and negative classes.

- The More-complex Model using Random Forest achieved an ROC AUC score of 0.9249. Compared to the Baseline Model, the Random Forest model shows an improvement in performance, as indicated by the higher ROC AUC score.

- The XGBoost Model achieved an ROC AUC score of 0.9294. This model shows a further improvement in performance compared to both the Baseline Model and the More-complex Model using Random Forest.

- The Tuned Random Forest Model achieved an ROC AUC score of 0.9222. Despite being tuned, this model's performance, as measured by the ROC AUC score, is slightly lower than the XGBoost Model but still higher than the Baseline Model and the More-complex Random Forest Model.

<div style="text-align:center;">
  <img src="Images/Models ROC curve.png" alt="ROC Curves">
</div>

<h1 style="text-align:center;">CONCLUSION</h1>

SyriaTel faces a significant challenge with customer churn, which poses both financial and reputational risks. Through comprehensive analysis and modeling, it's evident that predictive analytics can offer valuable insights into customer behavior and aid in proactive churn management. Among the models evaluated, XGBoost demonstrates superior performance in terms of accuracy, precision, recall, F1 score, and ROC AUC. Key features such as international plan status, customer service calls, and total day minutes emerge as crucial predictors of churn. Moving forward, SyriaTel should focus on implementing the recommendations oulined here.

<h3 style="text-align:center;">Recommendations</h3>

- **Implement targeted retention strategies: Utilize predictive insights to identify high-risk customers and deploy personalized retention tactics, such as tailored offers or proactive customer service interventions.**

- **Enhance customer experience: Invest in improving service quality and addressing pain points identified through customer feedback and analytics to foster loyalty and reduce churn.**

- **Continuously monitor and adapt: Regularly assess model performance and customer trends to refine predictive models and strategies, ensuring relevance and effectiveness over time.**

<h3 style="text-align:center;">Next Steps</h3>

- **Conduct deeper analysis: Explore additional data sources and factors influencing churn, such as customer demographics or usage patterns, to enhance predictive accuracy and identify new insights.**

- **Address model limitations: Address potential biases or limitations in the dataset, such as data imbalance or missing features , through data preprocessing techniques and model refinement to improve predictive performance and reliability.**

## Repository Guide

The datasets used can be found [here](<Data>)

The notebook can be found [here](<SyriaTel Customer Churn Prediction Model.ipynb>)

The presentation can be found [here](<SyriaTel Customer Churn Presentation.pdf>)
