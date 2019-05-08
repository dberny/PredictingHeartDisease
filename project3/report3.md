# How Best to Predict Heart Disease

## Diego Berny and Anna Griffin


[notebook](https://github.com/dberny/PredictingHeartDisease/blob/master/project3/project3.ipynb)


According to the CDC, heart disease is the [leading cause of death](https://www.cdc.gov/dhdsp/data_statistics/fact_sheets/fs_heart_disease.htm) in the US for both men and women]. We use data from real patients provided by the Cleveland Heart Disease Database to determine how accurately heart disease can be identified based on a number of different physical characteristics/measurements provided.

For a binary problem like this, the most natural approach is to apply logistic regression to the parameters in order to predict whether the person had heart disease. By applying this to the data, we were able to achieve an F1 score of just over 0.857. The F1 score considers how often the model correctly predicts a “positive” outcome (in this case having heart disease) versus the total times it predicts it as positive as well as how often it misses positive diagnoses and calls them negative. A perfect model would have an F1 score of 1, and it seems like logistic regression is not terribly far right off the bat.


This is a good start, but without context the number does not mean much; the more interesting question is whether heart disease can be predicted more accurately and effectively using different machine learning models that are readily available to anyone in today’s world.

A common classification method in machine learning is called [K-nearest-neighbors](https://towardsdatascience.com/machine-learning-basics-with-the-k-nearest-neighbors-algorithm-6a6e71d01761), where each datum is determined to be as part of a certain group based on what other points close to it are. When applied to the given dataset, 4 neighbors gave the best results on the training data.

![alt text](https://github.com/dberny/PredictingHeartDisease/blob/master/knn.png "K Nearest Neighbors Scores")

However, even this best result did not produce improved scores, not quite reaching a score of 0.85.

Another model that we tried was the random forest classifier. This method uses multiple decisions trees from the dataset to make the final prediction. After fitting the data to the model, the coefficient of determination was 0.88. This method is comparable to our baseline score with the logistic regression model but does not out perform it.


The logistic regression seemed to be the most accurate model for our data when comparing AUC scores. Our next exploratory decision was to analyze the features and use Feature Engineering techniques. Using `feature_importances`, we identify the features that have the least amount of importance and drop those to try and improve our model. Dropping features that are less important can improve our model as it eliminates potentially misleading data. The `'resting_ekg_results'`, `'sex'`, and `'fasting_blood_sugar_gt_120_mg_per_dl'` features received noticeably smaller values. We tried dropping these features and fit our logistic regression model to the updated training set. The average AUC score was almost the same as previous logistic regression score.

Another feature engineering method we used was binning data. There were a few features that had numerical data, like age and resting heart rate, that we wanted to bin. This would reduce potential noise within those features and hopefully yield more accuracy. The binning however did not seem to have a positive effect on the AUC score. The average score after using the 5-fold method was less than our baseline score which means that binning did not improve our model's performance.



Deep learning has been lauded as the answer to solving any number of problems people may tackle in the future ([or even just everything](https://www.alphr.com/the-future/1001614/are-ai-and-deep-learning-the-future-of-well-everything)), but reality seems to be a little less exciting than that. After training a deep learning model with one hidden layer on the data, the F1 score hovers around 0.83, still just a bit under the performance of logistic regression.
There is an argument that this model may not have worked as well as it could with more data, because heart disease depends on many factors which may not all be fully captured in less than just 200 patients, and an organization with access to a larger pool of data may have more success

At least for now, it might be a bit preemptive to assume that machine learning is the key to solving all the mysteries of the world. In the case of predicting heart disease, logistic regression does the same job while being more straightforward and less computationally expensive. However, the effectiveness of machine learning can only improve as techniques are improved and streamlined, so it can’t be totally written off either.

If you want to learn more about our process you can see our notebook [here](https://github.com/dberny/PredictingHeartDisease/blob/master/project3/project3.ipynb)
