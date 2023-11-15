# short-marketing-data-analysis
# Video Games: Data Analysis of gamers behaviors & Predictive Modeling 

Image visuals are in the notebook.

## 1) Objectives :

Segment the audience of gamers to predict the impact of evolutions in gameplays and business models on the performance of future games.
#### DISCLAIMER : All the data used here are generated in the next step, that's why analysis and predictions result may not provide as much insights as excpected
## 2) Data Generation
We need to create a simulated dataset, here's a quick overview that includes :

1) Sales and User Data

- The UBISOFT Game title 
- Purchase date
- Platform: The platform on which the user plays the game (PC, PS5, PS4 or Xbox).
- User ID
- Price
- In-game purchases or DLCs
  
2) Gamer User Behavior Data

- Hours played per game
- Game progression (levels or missions completed out of 100)
- Achievements unlocked (out of 50)
- Multiplayer vs. Single player mode usage (binary: 1 for multiplayer, 0 for single-player) 
- Reason for playing (scale from 1 to 5, with 5 being the highest motivation)
- Expectation score before playing (out of 10)
- Satisfaction score after playing (out of 10)

For simplicity, we'll focus on these small amount of features and generate a dataset for, say, 10,000 users.


## 3) Exploratory Data Analysis (EDA) :

Checked basic statistics (mean, median, etc.) of the dataset.
Visualized platform popularity using bar plots and analyzed the distribution of continuous variables using histograms or game in scaterplot.


## 4) Customer Segmentation using K-Means Clustering :

Normalized the data to ensure all features have the same scale.
We need to determine the optimal number of clusters. For that we used the Elbow Method. We've ploted the sum of squared distances (inertia) for different values of K to identify the "elbow" point, which gaves us a good estimate for the number of clusters (here we have choosen 7).​ 
Applied K-Means clustering and assigned cluster labels to each data point.

## 5) Cluster Analysis :

- Using barplot to view the amount of population in every cluster.
- Visualized cluster centers using scatter plots.
- Analyzed few characteristics of each cluster.
- Explored feature distributions within clusters using density plots.
- Correlation Heatmap (Here we can see that almost all data are correlated between them, it is due to the random data generation without bias, with real data this heatmap analysis gives insights about differents features, if a feature is very correlated wfith another one, it means that we can probably keep one of them.)
- Time pushases analysis by cluster (Monthly):
- 
## 6) Trend Analysis:

#### Adding more data to our dataset to simulate industry trends :

Generate New fictional data in order to do analyse external Industry Trends in the market and its alignment with our clusters

a) User Demographics:

- Age
- Gender
- Region

b) Game Preferences:

- Preferred Game Genre (Action, Adventure, Strategy, etc.)
- Importance of Graphics (Scale 1-10)
- Importance of Storyline (Scale 1-10)

c) Industry Trends:

- Game Duration
- Cross-Platform Gaming Interest
- Subscription Model Interest
- eSports Interest

Visualized the distribution of trends using pie charts.
Aligned the identified gamer segments with industry trends to predict which segments are likely to be influenced by upcoming changes.

#### Video Games Industry Trends alignments with our players

In this section we want to align our customer preferences (grouped by previous clusters) with the industry trends. Visualization shows us which clusters are more inclined towards each trend and give insights into which segments are more likely to be influenced by upcoming industry changes.

Examples : Gamers with high playtime might be more interested in Subscription Models as it could offer them a variety of games at a fixed cost ?
Younger gamers or those with high multiplayer usage might be more inclined towards Mobile Esports ?

## 7) Predictive Modeling for Trend Adoption (one target = industrial trend)  thanks to SK-Learn <3 (data science):
#### Insights :

Given the near-random nature of the data, the models are performing as expected. In practice, with a real dataset, we would anticipate clearer patterns and potentially better model performance.

In this section we have tried 4 differents types of algorithm :
- Logistic Regression
- Decision Tree
- Gradient Boosting
- Random Forest (composed of multiple decisions trees)

Predictions about influence on clusters :
Applied Logistic Regression and Decision Tree classifiers to predict a cluster's likelihood to adopt a trend based on its characteristics.
The decision tree model slightly outperforms the logistic regression model in terms of accuracy. However, the difference is marginal, and both models have their own strengths and applications. Logistic regression provides probabilities, which can be useful in certain scenarios, while decision trees offer more interpretable decision-making pathways.

We have explored advanced models or ensemble techniques like Random Forest and Gradient Boosting that might capture complex relationships better.

#### Feature Importance (concept) :

A powerful aspect of ensemble models like Random Forest and Gradient Boosting is their ability to rank features based on their importance. Feature importance can give us insights into which factors are most influential in determining user interests or behaviors. This can be especially valuable for marketing or game development teams, as it can guide decision-making processes.

#### Hyperparameter Tunning (concept) :

After difining the set of hyperparameters we wanna tune and by using GridSearchCV, we could performe an exhaustive search over the hyperparameters.
Train the model with the best hyperparameters found and evaluate its performance with another dataset for evaluation.

## 8) Churn Prediction (conceptual and now deleted):
In marketing, churn prediction is the fact that we identify users who are likely to stop using a product or service. For our context with our df, we'll define a user as "churned" if they didn't purshase a game for a certain period (e.g., the last year). Total hours played in the last month.

Issues with feature selection without more insightful data:
- Average satisfaction score of games played: Since each user has only one game, this will be the same as the satisfaction score for that game.
- Total hours played in the last month: This would just reflect the hours played for the one game the user has.
- Total number of games played: This will be 1 for all users.
- However, the feature "days since the last purchase" is still relevant since it indicates how recent the user's interaction was.

For meaningful churn prediction, having multiple interactions per user over time is crucial. This allows us to observe patterns or changes in user behavior leading up to the churn event. With only one interaction per user, it's challenging to infer any meaningful patterns or make robust predictions.
After cross validation I have deleted this part from my notebook.

## 9) Improvments | Limitations 

Clusters 0 and 3 potentially containing outliers. Addressing these outliers through data preprocessing could improve the model's performance. 
The correlation analysis (where most data appear correlated due to random generation) is an important point. In a real-world scenario, feature selection or dimensionality reduction might be applied if multicollinearity is detected.
We can incorporate external factors (e.g., economic indicators, technological advancements).
If working with real-world data, it can lead to more accurate and actionable insights.

Advanced Ensemble Techniques: We can explore more advanced ensemble methods like XGBoost, this algorithm often outperform traditional ensemble methods, especially on large datasets.

Hyperparameter Tuning: For our Random Forest and Gradient Boosting we could have various hyperparameters that can be tuned to optimize performance. However in this case we need real data, but we have already used techniques like grid search or random search.

Deep Learning: For complex datasets, deep learning models like neural networks can capture more patterns. Given sufficient data, it might be worth exploring, but we currently don't have those data.

Churn Prediction: Predicting which users might stop playing a game (churn) can be valuable. By identifying these users early, targeted marketing strategies can be developed to retain them.

Recommendation System: In the synthetic dataset we generated earlier, each user has only one game purchase, which doesn't provide a robust foundation for building a recommendation system. Usualy, recommendation systems thrive on datasets where users have interacted with multiple games.

