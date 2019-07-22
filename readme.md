# Executive Summary

Using the publicly available data set for IMDB ( https://www.imdb.com/interfaces/ ), we built a model that attempted to predict a movie's average rating. 
To measure the model's performance, we first used the average movie rating to establish a baseline accuracy of 80.24% where the average prediction was 0.99 points off. Using the model, we achieved 86.31% accuracy with the average prediction 0.69 points off. 

# Next steps - Business Use Cases

### [1] Predict profitable movies

One potential use case is to attempt to predict hit (or profitable) movies in the early stages of limited release or focus groups. This will inform the business on how to best invest the advertising budget. If we are really certain a movie will perform well, should the business invest / frontload additional advertising resources to get the movie to its critical mass? Or should the business pull back some of those resources to invest in other less certain ventures? 

### [2] Predict cult classics

Cult classics are different than regular movies in that they typically have a very dedicated fanbase that is likely to spend more money (viewing / merchandise) and spread the word. Also, cult classics historically do not perform that well in the initial release. Instead, over time (typically many years), the fanbase grows and the movie becomes immensely profitable. If we can predict a cult classic in advance, perhaps additional advertising exposure would allow the business to turn it into a hit many years in advance, thereby capturing additional revenue. 

# Next steps - Technical

One of the top predictors for a movie's average rating is the number of votes. In this case, correlation does not equate to causation. A movie's ratings will not go up simply because more people watch it, rather, more people watch the movie because of positive reviews they hear about it. In all of our use cases, we are looking to make predictions in the early stages, where movies will have a very small sample size of reviews. Instead, we would need to create additional variables to capture velocity of reviews / day, average rating / day, etc.

Also, bringing in additional data would greatly improve the predictive power. In the early stages of a movie, most IMDB reviews are from professional or self described film critics. To get a better sense of what the general population thinks (and sooner), we could scrape social media for sentiment of the movie. In the past, I built an application that scrapes, scores, and serves Twitter sentiment of a movie in real time. This could prove immensely valuable in terms of predictive power. Examples below:
[https://github.com/DansProjects/twitter_movie_sentiment_analysis][Classification + Kafka implementation]
[https://github.com/DansProjects/twitter_movie_flask][Internal API]
[https://github.com/DansProjects/twitter_movie_react][Real-time dashboard in React] 

Beyond sentiment, we could use the various text datasets from IMDB, Social Media, and even other sites like Rotten Tomatoes to predict average ratings. Additional variables to bring in could be budget - broken down into different levels, such as pre/post production, advertising, casting, sfx, film rights, etc.

Finally, due to computing restraints, I was not able to find the optimal parameters for the RandomForest. With more time, I would allow for more iterations, perhaps using GridSearch.