# Classification of Reddit Posts

### Overview

Reddit was first launched in 2005 as a social networking site based on a forum-style discussion structure. Communities (called subreddits) on Reddit are topic-based, where users can contribute to it through posts and interact with fellow users through comment threads. Users also participate in the community through voting "up" or "down" on content posted by others, which increases the exposure for posts with more upvotes in the Reddit homepage and subreddit feeds and reduces the same for downvoted content [1].

### Problem Statement

While Reddit is centered around users active participation with the respective communities, it also requires the help of moderators in ensuring the standard of content on the subreddits. The scope of work includes areas such as dispute settlement, implementation of ground rules and delete / edit content which is deemed unsuitable or irrelevant for the site. On this end, volunteers taking up the role of a moderator could chalk up to 466 hours of work daily which translates to about US$3.4 million worth of labour annually [2]. In the aspect of detecting irrelevant material, the development of an automated way to review the post content for its relevancy would help in reducing the workload on the moderators.

Delving specifically into the topics of statistics and machine learning, these are two very closely related fields as they are often used alongside each other in data analysis and data science. They also share key commonalities such as:
- Analyzing and extracting insights from data
- Making inferences about population based on sample data
- Utilizing probability distribution, likelihoods and statistical tests to quantify uncertainties and evaluate likelihood of different outcomes

However, they differ in their area of focus where statistics is concentrated on inference, model assumptions and interpretability, while machine learning focuses on prediction, optimization and algorithm design.

Thus, this project aims to apply Natural Language Processing (NLP) on the scraped text data and build a binary classification model to aid moderators in classifying new post content into the respective communities of statistics and machine learning more effectively by differentiating between the two fields.

### Data Source

The two subreddits which this analysis would be scrapping content from are:
- r/statistics (https://www.reddit.com/r/statistics/
- r/MachineLearning (https://www.reddit.com/r/MachineLearning/)

### Model Evaluation Criteria

The model would be evaluated based on 2 metrics:
1. Accuracy (ratio of true positives and true negatives to the sum of true positives, true negatives, false positives and false negatives); and
2. Specificity (ratio of true negatives to sum of true negatives and false positives)

The objective would be for the final selected model to:
1. Achieve an accuracy of at least 0.85; and
2. Attain a specificity of at least 50% higher than the baseline score

### Conclusion

To build a binary classification model to assist the reddit moderators in classifying new posts between the statistics and machine learning subreddits, the PRAW (Python Reddit API Wrapper) package is utilized to access Reddit's API and facilitate the scraping of posts from the respective subreddits. A total of 999 posts have been scraped from r/statistics while 981 posts have been scraped from the r/machinelearning. Data cleaning steps such as handling missing values, tokenization, lemmatization and removal of stop words were then performed to reduce noise and improve the quality of the text data. The text data is then being converted into a matrix representation to facilitate the subsequent modeling steps.

The Logistic Regression model was eventually selected as the final model to be used for the classification task. The model generated an accuracy of 0.96 and specificity of 0.96 on the test set, and has achieved the targets set out in the evaluation criteria.

### Recommendation & Future Steps

Overall, the content of the posts provides a good foundation in building an accurate binary classification model. Aside from being able to assist in classifying new posts to ensure relevancy of the subreddits, the moderator is able to use the Logistic Regression model to identify words that relate to the respective subreddit topics and their relative importance. This is illustrated in the earlier review of features based on the modeling, where it was established that words such as 'llm', 'ai', 'ml', 'model', 'machine', 'training', 'chatgpt', 'neural' are identified as being contextually related to the machine learning topic while words such as 'statistic', 'statistical', 'variable', 'stats', 'test', 'sample', 'variance', 'interval' are contextually related to the statistics topic. This model would also be relatively cost-effective to deploy due to its lower computational complexity and efficiency in working with large datasets.

While the model is already relatively accurate, further refinements could be explored in the following aspects:
1. Data cleaning: Perform a more thorough review and removal of stop words where necessary to further improve the quality of the text data.
2. Building of additional models: Modeling using other more advanced models such as Support Vector Machines and Gradient Boosting in an attempt to further improve the outcome.
3. Temporal analysis: Revise the scraping function to include the scraping of the posting date and time to analyse changes in keywords over time which may reveal trends and changes in the discussion on the subreddits.

### References

[1] Michelle Martin, "What is Reddit, and Should Your Brand Be Using It?", Hootsuite, 28 November, https://blog.hootsuite.com/what-is-reddit/#:~:text=Reddit%20is%20a%20social%20network,or%20%E2%80%9Cdown%E2%80%9D%20the%20algorithm.

[2] Chris Stokel-Walker, "Reddit moderators do $3.4 million worth of unpaid work each year", NewScientist, 24 June 2022, https://www.newscientist.com/article/2325828-reddit-moderators-do-3-4-million-worth-of-unpaid-work-each-year/#:~:text=The%20social%20news%20website%20relies,deemed%20unsuitable%20for%20the%20site.
