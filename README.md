# CryptoClustering
In this challenge, you'll use your knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

# Before You Begin
1. Create a new repository for this project called ![image](https://github.com/user-attachments/assets/61e9b6c4-3bd8-406a-82e1-982289cc073b). *Do not add this homework to an existing repository.*
2. Clone the new repository to your computer.
3. Push your changes to GitHub.

# Instructions
1. Rename the ![image](https://github.com/user-attachments/assets/01ab3b1a-6696-47fc-b779-695832631648) file as ![image](https://github.com/user-attachments/assets/f730de84-ae5d-4876-b62f-7b16f64de855).
2. Load the ![image](https://github.com/user-attachments/assets/b2fa3108-203d-43b1-a599-f3fd4d2e9feb) into a DataFrame.
3. Get the summary statistics and plot the data to see what the data looks like before proceeding.

# Prepare the Data
* Use the ![image](https://github.com/user-attachments/assets/b948a9da-abf8-4437-bde3-ce4d99b112f0) module from ![image](https://github.com/user-attachments/assets/51c65f20-387b-401c-960f-7badfbb4cde0) to normalize the data from the CSV file.
* Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

  * The first five rows of the scaled DataFrame should appear as follows:
 
    ![image](https://github.com/user-attachments/assets/eed1513b-9893-425e-9fb8-1fc391f70364)

# Find the Best Value for k Using the Scaled DataFrame

Use the elbow method to find the best value for ![image](https://github.com/user-attachments/assets/865c4fde-5bb5-4bed-9408-7983621f04dc) using the following steps:

* Create a list with the number of ![image](https://github.com/user-attachments/assets/6e89de9a-3247-458c-937b-5d7f46f03e5b) values from 1 to 11.
* Create an empty list to store the inertia values.
* Create a for loop to compute the inertia with each possible value of ![image](https://github.com/user-attachments/assets/24b43498-0fb7-4d00-b325-552dbe927f10).
* Create a dictionary with the data to plot the elbow curve.
* Plot a line chart with all the inertia values computed with the different values of ![image](https://github.com/user-attachments/assets/35b1c392-9a84-45e6-945d-c034b9db003b) to visually identify the optimal value for ![image](https://github.com/user-attachments/assets/d2dc09f7-8d43-4b7c-a057-c586c0792eca).
* Answer the following question in your notebook: What is the best value for ![image](https://github.com/user-attachments/assets/800c2b6b-7296-4793-b43d-923ddcc0520c)?
    
# Cluster Cryptocurrencies with K-means Using the Scaled DataFrame

Use the following steps to cluster the cryptocurrencies for the best value for ![image](https://github.com/user-attachments/assets/fd1fd7ad-d362-41eb-a1cd-3c14bf73a54c) on the scaled DataFrame:

* Initialize the K-means model with the best value for ![image](https://github.com/user-attachments/assets/4e5ddc46-e2e8-4990-8ea8-b6460055986d).
* Fit the K-means model using the scaled DataFrame.
* Predict the clusters to group the cryptocurrencies using the scaled DataFrame.
* Create a copy of the scaled DataFrame and add a new column with the predicted clusters.
* Create a scatter plot using hvPlot as follows:
  * Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
  * Color the graph points with the labels found using K-means.
  * Add the "coin_id" column in the ![image](https://github.com/user-attachments/assets/94127de1-7dbf-42f9-ae75-fb66ad7580bc) parameter to identify the cryptocurrency represented by each data point.
    
# Optimize Clusters with Principal Component Analysis
* Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.

* Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:

  * What is the total explained variance of the three principal components?

* Create a new DataFrame with the scaled PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

  * The first five rows of the scaled PCA DataFrame should appear as follows:

![image](https://github.com/user-attachments/assets/b2705ac2-6b7a-4211-8d5a-1568f7d402e0)

# Find the Best Value for k Using the PCA DataFrame
Use the elbow method on the scaled PCA DataFrame to find the best value for ![image](https://github.com/user-attachments/assets/5005c453-55d4-474b-852a-7a7f05cd85bb) using the following steps:

* Create a list with the number of k-values from 1 to 11.
* Create an empty list to store the inertia values.
* Create a ![image](https://github.com/user-attachments/assets/327ce46b-63e8-4310-8b49-5d84ab9294b7) loop to compute the inertia with each possible value of ![image](https://github.com/user-attachments/assets/04395291-6f83-4beb-823c-cbcd2ff55c9b).
* Create a dictionary with the data to plot the Elbow curve.
* Plot a line chart with all the inertia values computed with the different values of ![image](https://github.com/user-attachments/assets/c9a97a3e-f8a2-4345-a016-c03a28fe291e) to visually identify the optimal value for ![image](https://github.com/user-attachments/assets/939cf71e-ba6d-4edf-990f-c641bffb13b0).
* Answer the following question in your notebook:
  * What is the best value for ![image](https://github.com/user-attachments/assets/a7a7826d-1c19-42cc-b697-347c3c043af9) when using the scaled PCA DataFrame?
  * Does it differ from the best k value found using the original scaled DataFrame?

# Cluster Cryptocurrencies with K-means Using the PCA DataFrame
* Use the following steps to cluster the cryptocurrencies for the best value for ![image](https://github.com/user-attachments/assets/dbb2fabf-7809-4503-87b4-3d9be1448a04) on the PCA DataFrame:
* Initialize the K-means model with the best value for ![image](https://github.com/user-attachments/assets/2e79a2bc-6b37-42fe-87a7-1b85efa6b1fc).
* Fit the K-means model using the scaled PCA DataFrame.
* Predict the clusters to group the cryptocurrencies using the scaled PCA DataFrame.
* Create a copy of the scaled PCA DataFrame and add a new column to store the predicted clusters.
* Create a scatter plot using hvPlot as follows:
  * Set the x-axis as "PC1" and the y-axis as "PC2".
  * Color the graph points with the labels found using K-means.
  * Add the "coin_id" column in the ![image](https://github.com/user-attachments/assets/563dab3c-2af3-422f-b7d2-03e1f3206838) parameter to identify the cryptocurrency represented by each data point.

* Answer the following question:
  * What is the impact of using fewer features to cluster the data using K-Means?
 
 > ⏪ **REWIND**  
> Recall that you learned how to create composite plots in a previous module.  
> If you need a refresher, review that module.  
> You can also check [Composing Plots](https://holoviz.org/tutorial/Composing_Plots.html) in the hvPlot documentation.

# Requirements
# Find the Best Value for k by Using the Scaled DataFrame (15 points)
To receive all points, you must:
* Code the elbow method algorithm to find the best value for k. Use a range from 1 to 11. (5 points)
* To visually identify the optimal value for k, plot a line chart of all the inertia values computed with the different values of k. (5 points)
* Answer the following question: What's the best value for k? (5 points)
  
# Cluster the Cryptocurrencies with K-Means by Using the Scaled DataFrame (10 points)
To receive all points, you must:
* Initialize the K-means model with best value for k. (1 point)
* Fit the K-means model by using the scaled DataFrame. (1 point)
* Predict the clusters for grouping the cryptocurrencies by using the scaled DataFrame. Review the resulting array of cluster values. (3 points)
* Create a copy of the scaled DataFrame, and then add a new column of the predicted clusters. (1 point)
* Using hvPlot, create a scatter plot by setting ![image](https://github.com/user-attachments/assets/a1bdf902-de76-45d2-99f3-97aa12c07d39) and ![image](https://github.com/user-attachments/assets/c6ede0b4-fef4-41cf-b370-924cbf69c553). Color the graph points with the labels that you found by using K-means. Then add the crypto name to the ![image](https://github.com/user-attachments/assets/8014e02f-668a-46d4-98d0-e1341e8dcc10) parameter to identify the cryptocurrency that each data point represents. (4 points)

# Optimize the Clusters with Principal Component Analysis (10 points)
To receive all points, you must:
* Create a PCA model instance, and set ![image](https://github.com/user-attachments/assets/e6c62d9a-c720-4008-82af-5b3c594eeaf7). (1 point)
* Use the PCA model to reduce the features to three principal components. (2 points)
* Get the explained variance to determine how much information can be attributed to each principal component. (2 points)
* Answer the following question: What's the total explained variance of the three principal components? (3 points)
* Create a new DataFrame from the scaled PCA data. Be sure to set the ![image](https://github.com/user-attachments/assets/33c7e852-8dc2-4c93-b313-32a2860d1d9c) index from the original scaled DataFrame as the index for the new DataFrame. Review the first five rows of the DataFrame. (2 points)

# Find the Best Value for k by Using the PCA DataFrame (10 points)
To receive all points, you must:

* Code the elbow method algorithm, and use the scaled PCA DataFrame to find the best value for k. Use a range from 1 to 11. (2 points)
* To visually identify the optimal value for k, plot a line chart of all the inertia values computed with the different values of k. (5 points)
* Answer the following questions: What's the best value for k when using the scaled PCA DataFrame? Does it differ from the best value for k that you found by using the original scaled DataFrame? (3 points)

# Cluster the Cryptocurrencies with K-means by Using the PCA DataFrame (10 points)
To receive all points, you must:
* Initialize the K-means model with the best value for k. (1 point)
* Fit the K-means model by using the PCA data. (1 point)
* Predict the clusters for grouping the cryptocurrencies by using the PCA data. Review the resulting array of cluster values. (3 points)
* Create a copy of the scaled PCA DataFrame, and then add a new column of the predicted clusters. (1 point)
* Using hvPlot, create a scatter plot by setting ![image](https://github.com/user-attachments/assets/67a4cb70-30d8-4786-8044-7b388d2fff18) and ![image](https://github.com/user-attachments/assets/201a3ac3-d233-4ab7-b9a6-0613f9cd5179). Color the graph points with the labels that you found by using K-means. Then add the crypto name to the ![image](https://github.com/user-attachments/assets/0dc3ab0e-eddc-4c29-a05a-ff1700a4c84d) parameter to identify the cryptocurrency that each data point represents. (4 points)

# Visualize and Compare the Results (15 points)
To receive all points, you must:
* Create a composite plot by using hvPlot and the plus sign (![image](https://github.com/user-attachments/assets/cf951ff6-2da5-4481-97b3-c577009a3761)) operator to compare the elbow curve that you created from the original scaled DataFrame with the one that you created from the scaled PCA DataFrame. (5 points)
* Create a composite plot by using hvPlot and the plus (![image](https://github.com/user-attachments/assets/9602fdda-6da4-4147-a3ce-81ac51e9d1a1)) operator to compare the cryptocurrency clusters that resulted from using the original scaled DataFrame with those that resulted from the scaled PCA DataFrame. (5 points)
* Answer the following question: Based on visually analyzing the cluster analysis results, what's the impact of using fewer features to cluster the data by using K-means? (5 points)

# Coding Conventions and Formatting (10 points)
To receive all points, you must:
* Place imports at the top of the file, just after any module comments and docstrings, and before module globals and constants. (3 points)
* Name functions and variables with lowercase characters, with words separated by underscores. (2 points)
* Follow DRY (Don't Repeat Yourself) principles, creating maintainable and reusable code. (3 points)
* Use concise logic and creative engineering where possible. (2 points)

# Deployment and Submission (10 points)
To receive all points, you must:
* Submit a link to a GitHub repository that's cloned to your local machine and that contains your files. (4 points)
* Use the command line to add your files to the repository. (3 points)
* Include appropriate commit messages in your files. (3 points)

# Code Comments (10 points)
To receive all points, your code must:
* Be well commented with concise, relevant notes that other developers can understand. (10 points)

# References
Data for this dataset was generated by edX Boot Camps LLC, and is intended for educational purposes only.
