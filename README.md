# short-marketing-data-analysis
# Analysis of gamers behaviors
In this 

## Data Generation
We need to create a simulated dataset, here's a quick overview  that includes:

1) Sales and User Data

- Game title 
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

## User Segmentation
We need to determine the optimal number of clusters. For that we will use the Elbow Method. We'll plot the sum of squared distances (inertia) for different values of K to identify the "elbow" point, which will give us a good estimate for the number of clusters.​




User Demographics:

Age
Gender
Region
Game Preferences:

Preferred Game Genre (Action, Adventure, Strategy, etc.)
Importance of Graphics (Scale 1-10)
Importance of Storyline (Scale 1-10)
Industry Trends:

VR Gaming Adoption
Cross-Platform Gaming Interest
Subscription Model Interest
Mobile Esports Interest



## Video Games Industry Trends alignments with our players

In this section we want to align our customer preferences (grouped by previous clusters) with the industry trends. Visualization shows us which clusters are more inclined towards each trend and give insights into which segments are more likely to be influenced by upcoming industry changes.

Examples : Gamers with high playtime might be more interested in Subscription Models as it could offer them a variety of games at a fixed cost ?
Younger gamers or those with high multiplayer usage might be more inclined towards Mobile Esports ?

## Predictions about influence on clusters :
Insights :

Given the near-random nature of the data, the models are performing as expected. In practice, with a real dataset, we would anticipate clearer patterns and potentially better model performance.

The decision tree model slightly outperforms the logistic regression model in terms of accuracy. However, the difference is marginal, and both models have their own strengths and applications. Logistic regression provides probabilities, which can be useful in certain scenarios, while decision trees offer more interpretable decision-making pathways.

## Improvments 
For a more holistic prediction, external factors (e.g., economic indicators, technological advancements) can be incorporated.