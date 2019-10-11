
Name: Yeqing Liu (yl1032)

Introduction
This project works on the dataset that contains the data about comments on reddit, and all these comments are from Oct, Nov and DEC of 2018 and JAN of 2019. The aim of this project is to dicover the relationship between score and other variables of the most popular 5 subreddits:'politics','nfl','funny','nba','The_Donald'. The code and result of this project was written in the file named 'miniproject.ipynb'.

Method:
To explore the data, firstly, I was interested in top 10 subreddits that these comments are on. Therefore, I ploted a bar chart to visualize the number of each subreddit. As the chart represents, the most popular 10 subreddits are 'AskReddit','politics','nfl','funny','nba','The_Donald','worldnews','CFB','gaming','FortNiteBR'. These top 10 subreddits cover topics including politics, sports, and entertainment. As 'AskReddit' is a too broad subreddit that may contain many subjects, I only focused on the 5 subreddits upon 'AskReddit'. The mean value of the score, which is 9.16, and I also plotted the histogram of scores of the 5 most popular subreddits to have an overall distribution of their scores. The histogram of scores shows a roughly normal distribution.

Before doing the feature engineering, I selected some variables and hypothesized that they may be useful to predict scores, these variables were "author", "parent_id"," account_create_time", "comment_create_time", "edited", "is_submitter", "score", "subreddit". Then, I did the feature engineering by adding a new column 'account_year' to the dataset, which represents the the year of creating the account. I added this varible becuase I think that the number of years of creating an account would be an significant variable to explain the score. Since I noticed that there are some null values in 'account_year' and 'score', I cleaned data by filter out data, where 'account_year'=null and 'score'=null and then obtained the data with those top 5 popular subreddits.

I built a supervised linear model to predict the score for the most popular 5 subreddits that I obtained in the first step based on 4 predictors. The linear regression is: score= if_edit + if_submitter + account_year + subreddit_class.
The data is splited into training data(80%) and test data(20%).


Results:
The result shows that score=21.9*if_edit + 0*if_submitter   -0.122*account_year + 0.0*subreddit_class = 21.9*if_edit - 0.122*account_year, and R-Squared=0.68%, RMSE=128 . Obviousely, the training RMSE is too big and R-squared is too low. After predicting on the test data, the result shows that R-Squared= 0.66%, RMSE=128.87, which are also too bad to accept. In conclusion, my linear regression model is not good. The reasons for the invalidation of the model may be that these varibales I used in the regression are not very significant. In addition, 'score' is a very subjective term, it also depends on the hot news and affairs at that time. Therefore, there is no definite trend and parttern that we could use to predict score.


Discussion and Further Work:
However, there are some aspects that could be used to improve the model. Before modelling, we could do some hypothesis tests to define the significance of features. Furthermore, if we get more data about the users, we could discover more on the points that we are interested in.



