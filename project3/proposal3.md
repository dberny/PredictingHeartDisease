# Predicting Heart Disease

### Diego Berny and Anna Griffin


### The Data

For this project, we are taking part in a competition hosted by DrivenData, in which the goal is to predict whether a certain patient has/will have heart disease based on a number of factors like sex, age, blood pressure, and a number of other medical characteristics. The dataset they provide comes from a study on heart disease from the Cleveland Heart Disease Database that is publicly available. They also explicitly call out that their data is available for use in external projects. They have already split the data into training and test sets, and have made those available as csv files [here](https://www.drivendata.org/competitions/54/machine-learning-with-a-heart/data/).

There is some concern about privacy because we are using real people's medical history for our project. However, the labels attached to each person are totally anonymous. In addition, we will use each person to learn about heart disease and what its predictors may be, but will not be publishing data about any one person in particular.



### Exploration

Heart disease being the top cause of death in the United States making it an important and relevant topic to our lives today. We both want to explore the machine learning space and were interested in this competition provided by DrivenData. The goal of our project is to be able to predict the chances that a given person has heart disease. This will allow doctors to provide better treatment and help improve preventative care. We plan to use the `scikit-learn` library and the log loss classification function to asses our performance.
