# Bayesian Machine Learning Final Project

This repository includes the jupyter notebooks that were used in assessing the uncertainties in classifcation of tornadoes. The models we used include: [Mixed Naive Bayes](https://github.com/prabsingh1/bayesian_tornado/blob/main/tornados-Naive%20Bayes.ipynb), [Multinomical Logistic Regression](https://github.com/prabsingh1/bayesian_tornado/blob/main/tornados-Naive%20Bayes.ipynb), and Hierarchical Multinomical Logisitc Regression. 

We obtained our [data](https://github.com/prabsingh1/bayesian_tornado/blob/main/1950-2018_all_tornadoes.csv) from the National Oceanic and Atmospheric Administration (NOAA) database. The dataset contains tornado-related variables such as location, fatality, length, width, and damage. We were also interested in the weather conditions leading up to the tornadoes, hence, we [web-scraped](https://github.com/prabsingh1/bayesian_tornado/blob/main/tornado_obs_combining.R) the weather conditions for 1 hour and 2 hours prior to the onset of the tornadoes using R. Our goal here was to learn whether we can assess the uncertainty of classifying tornadoes using Bayesian methods. 

## Mixed Naive Bayes model

Since our dataset contains both categorical and numeric variables, we started with a [mixed Naive Bayes approach](https://github.com/prabsingh1/bayesian_tornado/blob/main/tornados-Naive%20Bayes.ipynb): multinomial for categorical data and Gaussian for numerical data. From here, the probability of an observation belonging to a class is simply the product of both of the categorical and numerical naive bayes probabilities. The class with the greatest probability is the determined class, or in this case magnitude, of the tornado. 

## Multinomial Logistic Regression 

Since our response variable is categorical with more than two classes, we modeled our data using a [multinomial logistic regression model](https://github.com/prabsingh1/bayesian_tornado/blob/main/tornados-Naive%20Bayes.ipynb). Multinomial logistic regression uses a softmax function to compute the regression parameters, as opposed to the sigmoid function used in binary logistic regression.    


## Hierarchical Multinomial Logistic Regression 

We also modeled this data as a hierarchical multinomial logistic regression [hierarchical multinomial logistic regression model](https://github.com/prabsingh1/bayesian_tornado/blob/main/tornados-hierarchical.ipynb). Our assumption was that the weather and climates in different states vary and this could have an impact on the strength of tornadoes. A hierarchical model allowed us to have a different slope and intercept for each state. Since states can share weather characteristics, we also used the hierarchical modeling to group states together into regions to compute the posterior probabilities and to determine the predictive power of the model.  
