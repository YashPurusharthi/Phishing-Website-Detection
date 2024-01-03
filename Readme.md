Model to predict whether a given website is a Phishing website.

The model takes an input of 29 attributes based on a given URL to predict whether a given website is a phishing website or not.

The set of input attributes/features includes:
[ having_IP_Address, URL_Length, Shortining_Service, having_At_Symbol, double_slash_redirecting, Prefix_Suffix, having_Sub_Domain, SSLfinal_State, Domain_registeration_length, Favicon, port, HTTPS_token, Request_URL, URL_of_Anchor, Links_in_tags, SFH, Submitting_to_email, Abnormal_URL, Redirect, on_mouseover, RightClick, Iframe, age_of_domain, DNSRecord, web_traffic, Page_Rank, Google_Index, Links_pointing_to_page, Statistical_report ]

Each feature has a value of [-1, 0, 1]
e.g. consider feature having_IP_Address its value can be decided as
     -1: if it is hard to identify or information is missing.
     0: The given URL does not contain IP_Address in it.
     1: The given URL contains IP_Address in it.

Start with building our Model

1] Import all the required libraries

2] Load the Dataset
Mounting Google Drive as the dataset is stored in the drive.

3] Check for null values in the given dataset.
In this case, no null values are present.

4] Checking for Unique values in each column.
To get an idea about the dataset and handle categorical data.

5] Checking for Data Distribution of the given Dataset concerning Target Variable.
If Data Distribution is not proper it might lead to Bias in our model.

6] Check for colinearity between features and target variables.

7] Dropping features with zero colinearity with the Target variable.
If there is zero colinearity between the feature and target value that indicates the feature does not affect the Target variable so drop the feature to avoid overfitting.

8] Checking for Outliers.
No outliers were found.

9] Splitting Dataset
Splitting dataset into train and test dataset.
Train dataset to train our model and test dataset to check our model performance.

10] Load Model. 
In this scenario, we choose RandomForestClassifier based on:
Our Target is to classify whether True or False so a classification model.
Secondly, our features have a high colinearity between them so we cannot use the Linear Model so go with a tree structure.

We could have done scaling or normalization to reduce colinearity but it would have changed the values and in this case, each feature is a classification variable [1,0].

11] Hyper Parameter Tuning.
We are using the GridSearchCV method to find the best hyperparameters for our model.

12] Train Model.
By fitting the training dataset from the previous split.

13] Predict.
Give the testing dataset input to the model and store the predictions made by the model in a variable predictions_rf.

14] Check Accuracy.
To check the accuracy of the given model use predictions made by the model and compare them with actual values in the testing dataset.
We can observe an accuracy of 96% in our model.

15] Plot Confusion Matrix and Classification Report to further understand our model prediction.
The confusion matrix provides us with Total True Positive, False Positive, True Negative, and False NEgative predictions made by our model.