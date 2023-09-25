# reddit_classification

## Subreddit Classification Modeling Summary

### This project's goal was to use Reddit's API to web-scrape data from 2 different subreddits and use the content of each post or the title of each post to predict which subreddit it came from using a Natural Language Processing model.


### Data Collection, Cleaning, and Natural Language Processing
#### I collected a total of 1432 posts (comments) from the Python, Javascript, and Java subreddits. 722 from Python and 710 from Javascript and Java collectively. I used Reddit's API to gather the data and I filter my requests to avoid pulling any empty posts. I created functions to fetch the data, clean it, create a DataFrame, and create the features. Each subreddit post/comment has a title and text. The text can be viewed as the body of the post. I Lemmatized and Stemmed the text and title of each subreddit post and placed the output in a new DataFrame, which is what will be used for modeling.

### Data Modeling
#### I created eight Logisitic Regression, K-Nearest Neighbors, Decision Tree, and Naive Bayes classifiers. A total of thirty-two models. For each type of classifier, four were created using CountVectorizer and four with TfidfVectorizer. In all models English stop words were removed from the data. In each iteration a Grid Search was conducted to determine the best hyperparamters for both vectorizers max features and n_gram range. The best performing model was when I used the lemmatized titles with CountVectorizer and the Logistic Regression Classifier. This model had an accuracy score of 83%, balanced accuracy score of 83%, and a RocAuc score of .89. The words that drove the model's predictions most were like, write, scraping, chatbot, django, typescript, browser, react, spring, and askjs.

### Conclusions and Recommendations

#### If using posts from a subreddit to predict, which subreddit they came from is important to then this model could be deployed to accomplish that task. Additionally it can provide insight into what words are driving the model to predict a particular subreddit classification. For future research, I recommend attempting to model with a RandomForestClassifier, GradientBoostClassifier, and AdadBoostClassifier. Based on the performance of my models, I would expect these three to perform well. 

### Sources

#### Python - https://www.reddit.com/r/Python/
#### Java - https://www.reddit.com/r/java/
#### Javascript - https://www.reddit.com/r/javascript/
