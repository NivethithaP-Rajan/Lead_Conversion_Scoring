# Lead_Conversion_Scoring
Problem Statement
X Education sells online courses to industry professionals. The company markets its courses on several websites and search engines like Google
Although X Education gets a lot of leads to the course, its lead conversion rate is very poor. For example, if, say, they acquire 100 leads in a day, only about 30 of them are converted.
To make this process more efficient, the company wishes to identify the most potential leads, also known as ‘Hot Leads’. We need to build a model wherein you need to assign a lead score to each of the leads such that the customers with higher lead score have a higher conversion chance and the customers with lower lead score have a lower conversion chance. 

Solution Strategy
1.	Reading and Cleaning the Date:

The data was loaded and skimmed through to understand it. We had to deal with null values in few columns and the option ‘select’ had to be replaced with a null value since it did not give us much information. Few of the null values were changed to ‘Information not available’ so as to not lose much data, even though these columns were later removed while making dummies. We also used imputation techniques to treat few columns.

2.	Data Analysis:

We moved on to Exploratory Data Analysis of the dataset to get a feel of how the data is oriented with the Target variable. In this step, there were around 3 variables that were identified to have only one value in all rows. These variables were dropped.

3.	Creating Dummy Variables:

We created dummy variables for the categorical variables and dropped these original columns.

4.	Train – Test Split:

We then divided the dataset into test and train sections with a proportion of 70-30% values.

5.	Feature Rescaling:

We used the Min Max Scaling to scale the original numerical variables. Then using the stats model we created our initial model, which would give us a complete statistical view of all the parameters of our model.

6.	Feature selection using RFE:

Using the RFE method we selected 15 top features. We then built models and recursively generated statistics and looked at P-values in order to select the most significant values that should be present and dropped the insignificant values.

By doing this we arrived at 10 most significant values. We also made sure the VIF’s of these variables were below 5.

We then created the data frame having the converted probability values and we had an initial assumption that a probability value of more than 0.5 means 1 else 0. Based on the above assumption, we derived the Confusion Metrics and calculated the overall Accuracy of the model. 
We also calculated the other metrices like ‘Sensitivity’, ‘Specificity’, Precision and Recall to understand how reliable the model is.

7.	ROC Curve:

We then plotted the ROC curve for the features and the curve came out be pretty decent with an area coverage of 88% which further solidified the of the model.

8.	Finding the Optimal Cutoff Point:

Then we plotted the probability graph for the ‘Accuracy’, ‘Sensitivity’, and ‘Specificity’ for different probability values. The intersecting point of the graphs was considered as the optimal probability cutoff point. The cutoff point was found out to be 0.35.
Based on the new value we could observe that close to 81% values were rightly predicted by the model. 
We could also observe the new values of the ‘accuracy=80.2%, ‘sensitivity=81%’, ’specificity=79.7%’.

9.	Computing Precision and Recall metrics

We also found out the Precision and Recall metrics values came out to be 78% and 67% respectively on the train data set.

10.	Making Predictions on Test Set
         Then we implemented the learnings to the test model and calculated the conversion 
          probability based on the Sensitivity and Specificity metrics and found out the accuracy value 
          to be 79.4%; Sensitivity=81.4%; Specificity= 78.2%.
