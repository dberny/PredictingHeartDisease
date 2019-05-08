# How Best to Predict Heart Disease

## Diego Berny and Anna Griffin


[notebook](newlink)


According to the CDC, heart disease is the leading cause of death in the US for [both men and women](https://www.cdc.gov/dhdsp/data_statistics/fact_sheets/fs_heart_disease.htm). We use data from real patients provided by the Cleveland Heart Disease Database to determine how accurately heart disease can be identified based on a number of different physical characteristics/measurements provided.

For a binary problem like this, the most natural approach is to apply logistic regression to the parameters in order to predict whether the person had heart disease. By applying this to the data, we were able to achieve an F1 score of just over 0.857. The F1 score considers how often the model correctly predicts a “positive” outcome (in this case having heart disease) versus the total times it predicts it as positive as well as how often it misses positive diagnoses and calls them negative. A perfect model would have an F1 score of 1, and it seems like logistic regression is not terribly far right off the bat.


This is a good start, but without context the number does not mean much; the more interesting question is whether heart disease can be predicted more accurately and effectively using different machine learning models that are readily available to anyone in today’s world.

A common classification method in machine learning is called [K-nearest-neighbors](https://towardsdatascience.com/machine-learning-basics-with-the-k-nearest-neighbors-algorithm-6a6e71d01761), where each datum is determined to be as part of a certain group based on what other points close to it are. When applied to the given dataset, 4 neighbors gave the best results on the training data. However, even the best result did not produce noticeably improved scores.

[RESULT SCORE HERE]


Deep learning has been lauded as the answer to solving any number of problems people may tackle in the future ([or even just everything](https://www.alphr.com/the-future/1001614/are-ai-and-deep-learning-the-future-of-well-everything)), but reality seems to be a little less exciting than that. After training a deep learning model with one hidden layer on the data, the F1 score hovers around 0.83, still just a bit under the performance of logistic regression.
There is an argument that this model may not have worked as well as it could with more data, because heart disease depends on many factors which may not all be fully captured in less than just 200 patients, and an organization with access to a larger pool of data may have more success

At least for now, it might be a bit preemptive to assume that machine learning is the key to solving all the mysteries of the world. In the case of predicting heart disease, logistic regression does the same job while being more straightforward and less computationally expensive. However, the effectiveness of machine learning can only improve as techniques are improved and streamlined, so it can’t be totally written off either.



![alt text](https://github.com/annagriffin/PoliceShootings/blob/master/project2/images/map.png "Map of deaths per state")

After controlling for population, we were able to identify states that stick out. Arizona, New Mexico, Oklahoma, and Alaska have the most deaths per person. On the other hand, there is a cluster of states in the North East that have the fewest deaths per person.

If you want to learn more about our process you can see our notebook [here](https://github.com/annagriffin/PoliceShootings/blob/master/project2/project2.ipynb)
