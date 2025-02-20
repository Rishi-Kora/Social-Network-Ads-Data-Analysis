# Social-Network-Ads-Data-Analysis<br>
Exploratory Data Analysis - Social Network Ads Data<br>
In this repository, I have taken Social Network Ads data from Kaggle and I have done:<br>
1. Data Loading and Initial Exploration:<br>
The analysis commenced with loading the dataset using the pandas library's read_csv() function, specifically targeting the "Social_Network_Ads.csv" file located in the user's Google Drive. Preliminary data exploration was conducted to understand its structure and characteristics. This involved:<br>

Missing Value Assessment: <br> Utilizing df.isna() and df.info() to confirm the absence of missing values in the dataset.
Data Shape and Structure: Examining the dataset's dimensions and column names using df.shape and df.columns, respectively, revealing 400 rows and 5 columns initially.<br>

Basic Statistical Summary:<br> Employing df.describe().transpose() to generate descriptive statistics for numerical features like Age and EstimatedSalary.<br>

Data Preview: <br> Displaying the first and last few rows of the dataset using df.head() and df.tail() for an initial overview of the data.<br>

2. Data Cleaning and Preprocessing:<br>

To ensure data quality and prepare it for modeling, the following cleaning and preprocessing steps were undertaken:<br>

Irrelevant Feature Removal: <br> The 'User ID' column was deemed irrelevant for modeling and removed using df.drop().<br>

Categorical Feature Encoding:<br> The 'Gender' feature was transformed from categorical (Male/Female) to numerical representation (0/1) using Label Encoding for compatibility with machine learning algorithms. This was confirmed by checking the unique values of 'Gender' after encoding.<br> 

Duplicate Entry Removal:<br> Duplicate rows were checked for using df.duplicated().sum(), and although none were found, the code includes a step to remove them using df.drop_duplicates() as a precautionary measure.<br>

Outlier Handling:<br> Outliers were detected based on z-scores calculated using scipy.stats.zscore() applied to numerical features. Data points exceeding a threshold of 3 were filtered out using a boolean mask to mitigate the impact of extreme values on model performance. The descriptive statistics of the outlier-removed dataset were then examined.<br>
3. Feature Correlation Analysis:<br>

To gain insights into relationships between features, a correlation heatmap was generated using sns.heatmap(). This visualization aids in understanding the degree of association between different variables, including Gender, Age, EstimatedSalary, and Purchased.<br>

4. Data Splitting and Scaling:<br>

Prior to model training, the dataset was divided into training and testing subsets using train_test_split() with a test size of 30% and a random state of 42. This partitioning enables model evaluation on unseen data to assess its generalization capability. Numerical features (Gender, Age, EstimatedSalary) were then scaled using StandardScaler() to ensure that features with different scales do not disproportionately influence the model's learning process.<br>

5. Model Building and Evaluation (Logistic Regression):<br>

A Logistic Regression model was trained using the preprocessed data to predict the target variable 'Purchased'. Model performance was assessed using the following metrics:<br>

Mean Absolute Error (MAE):<br> Measures the average absolute difference between predicted and actual values.<br>

Mean Squared Error (MSE):<br> Measures the average squared difference between predicted and actual values.<br>
Root Mean Squared Error (RMSE):<br> The square root of MSE, providing a measure of prediction error in the original unit.<br>

R-squared (R2):<br> Represents the proportion of variance in the target variable explained by the model. The calculated metrics were printed to the console.<br>
6. Model Persistence and Retrieval:<br>

The trained model and scaler were saved using the pickle library to separate files ('Social_Network.pkl' and 'scaler.pkl'), allowing for later retrieval and reuse without retraining. This facilitates model deployment and application to new data. The notebook explicitly confirms the successful saving of the model and scaler.<br>

7. Prediction on New Data:<br>

The loaded model and scaler were utilized to demonstrate the prediction process on a new dataset, specifically predicting the purchase likelihood for a 35-year-old male with an estimated salary of $60,000. This showcases the practical application of the trained model for making predictions on unseen instances. The prediction result was printed to the console.<br>

8. Enhanced Visualizations:<br> Incorporating a wider range of visualizations, such as histograms, scatter plots, and box plots for individual features, would provide deeper insights into data distributions and relationships. Visualizing the model's decision boundary could also be beneficial.<br>

Feel free to download the code and data.
