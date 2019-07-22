# Executive Summary

Using the publicly available data set for IMDB ( https://www.imdb.com/interfaces/ ), we built a model that attempted to predict a movie's average rating. 
To measure the model's performance, we first used the average movie rating to establish a baseline accuracy of 80.24% where the average prediction was 0.99 points off. Using a XGBoost model, we achieved 86.73% accuracy with the average prediction 0.67 points off. Given the opportunity and resources to collect and process more data, we believe that the accuracy can be improved considerably. The next steps depend on the business' use cases, though we have outlined a few suggestions below. 

# Next steps - Potential use Cases

### [1] Predict profitable movies

One potential use case is to attempt to predict hit (or profitable) movies in the early stages of limited release or focus groups. This will inform the business on how to best invest the advertising budget. If we are really certain a movie will perform well, should the business invest / frontload additional advertising resources to get the movie to its critical mass? Or should the business pull back some of those resources to invest in other less certain ventures? 

### [2] Predict cult classics

Cult classics are different than regular movies in that they typically have a very dedicated fanbase that is likely to spend more money (viewing / merchandise) and spread the word. Also, cult classics historically do not perform that well in the initial release. Instead, over time (typically many years), the fanbase grows and the movie becomes immensely profitable. If we can predict a cult classic in advance, perhaps additional advertising exposure would allow the business to turn it into a hit many years in advance, thereby capturing additional revenue. 

# Next steps - Additional Data

One of the top predictors for a movie's average rating is the number of votes. In this case, correlation does not equate to causation. A movie's ratings will not go up simply because more people watch it, rather, more people watch the movie because of positive reviews they hear about it. In all of our use cases, we are looking to make predictions in the early stages, where movies will have a very small sample size of reviews. Instead, we would need to create additional variables to capture velocity of reviews / day, average rating / day, etc.

Also, bringing in additional data would greatly improve the predictive power. In the early stages of a movie, most IMDB reviews are from professional or self described film critics. To get a better sense of what the general population thinks (and sooner), we could scrape social media for sentiment of the movie. In the past, I built an application that scrapes, scores, and serves Twitter sentiment of a movie in real time. This could prove immensely valuable in terms of predictive power. 

Examples below:
* [Classification + Kafka implementation](https://github.com/DansProjects/twitter_movie_sentiment_analysis)
* [Internal API] (https://github.com/DansProjects/twitter_movie_flask)
* [Real-time dashboard in React] (https://github.com/DansProjects/twitter_movie_react)

Beyond sentiment, we could use the various text datasets from IMDB, Social Media, and even other sites like Rotten Tomatoes to predict average ratings. Additional variables to bring in could be budget - broken down into different levels, such as pre/post production, advertising, casting, sfx, film rights, etc as well as attributes about the production company and financers.

Finally, it may be helpful to bring in data from TV Shows. This may be especially useful in predicting ratings for actors/directors/writers who are newer to movies and do not have many ratings.

# Files

* IMDB_DataPrep.ipynb - contains most of the data collection and data prep code. 
* IMDB_EDA.ipynb - very basic data analysis - lacking due to time / scope constraints
* IMDB_Modeling.ipynb - creates predictive model using RandomForest and XGBoost

# Additional time / resources

Due to computing restraints, I was not able to find the optimal parameters using Grid Search and settled for Randomized Search instead. I would have removed the 'unimportant' features as defined by the RandomForest and rerun the models.

Also, if given the business use case, I would have spent a lot more time in the data analysis part and done more research to understand the movie indsutry. Often-times, the importance of domain knowledge is understated. 