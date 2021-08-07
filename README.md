# Project 3: Subreddit Webscraping, NLP and Modeling


### Problem Statement
We quite often browse website everyday. we want to know the person's opinions from the posts by using sentiment analysis. We also want to understand the category where the new posts belong to. There are subreddit: r/cars https://www.reddit.com/r/cars/ and r/travel https://www.reddit.com/r/travel/. We will use our models to differentiate whether the posts are from r/travel or r/cars. 


### Project Flow
1. Data Gather
We gathered data from two subreddits by using the Pushshift API. We adjusted the parameters to collect 100 days data. Originally the data size is 19500 rows X 85 columns. we then will clean the data. 

2. Data clean
We did data cleaning in order to process the vectorization and modeling. The data cleaning processes include: Drop all missing values, Remove ‘removed’, ‘deleted’ reddit moderator words, URLs,  certain reddit markdown,  punctuation,  multiple consecutive blanks or spaces, non-ASCII characters, Stopwords(English)
Combined columns (‘subreddit’, ‘selftext’, ‘title’) > combine(‘selftext’ & ‘title) as ‘fulltext’. After this process, our data size is 4863 rows X 2 columns


3. NLP and EDA
We are now in the NLP process. I conducted the sentiment analysis on words and sentences to figure the whether the  posts are postive or negative opinions. I also found the post length to figure out the frequency of the post length. By analyzing the word frequency, we can tell which words are most often used in the post in subreddit. Overall, we had an overview and understanding of the posts. 

4. Modeling
We used machine learning models to analyze the posts to see performance of the predictions. Our goal is to predict whether the new post belongs to r/cars or r/travel category. It's a binary problem. We first set up our basline classifier. We used logistic regression, lasso regression, ridge regression, naive bayes multinomial classifier, random forest, SVM as models to do the analyses and predictions. We did hyperparameters tuning to find the optimal models as well. We then compared these models with the test accuracy scores. We also did roc auc metrics analysis to check the efficacy of these models. 

5. Result
a. we found most of the posts and comments are postive opinions through sentiment analysis.
b. we found redditors preferred to post title no more than 50 spaces, and wrote comments no more than 500 spaces. This is one of the typing behaviors. 
c. The most frequent words in each subreddit are overlap, but still there is a difference between the two categories.
d. We built several models to do the analysis and predicitons and naive bayes multinominal classifier is the best model to predict posts category. 
e. Testing accuracy scores -> Multinominal NaiveBayes:  Accuracy: 0.9849108367626886
Logistic Regression: Accuracy: 0.9801097393689986
Lasso Regression :  Accuracy: 0.9684499314128944
Ridge Regression:  Accuracy: 0.9595336076817559
KNN:  Accuracy: 0.6550068587105624
Random Forest:  Accuracy: 0.96639231824417
SVM:  Accuracy: 0.958161865569273
f. Except for knn and random forest, all other models' AUC scores are higher. 

### Conclusion 
a. We now are able to build models to predict the posts category in Reddit.
b. Naive Bayes Multinomial Classifier is relatively more accurate in this case to predict. 
c. All models' scores are promising and the reason could be r/travel and r/cars posts are relevant to each others by nature.


### Executive Summary
Our goal is to predict the categories of the new posts in reddit. We first pulled the 100 days data from two subreddits r/cars and r/travel by using pushshift API, then we past the data cleaning steps to make the data ready for vectorizaiton and EDA. At the vectrization steps, we analyze the postive/negative opinions the posts reflected by conducting sentiment analysis. We figured out the lenght of posts and  10 most frequent words that redditors used in these two subreddit, indicating the writing behaviors and topics relevance.
We started to built machine learning models using regression and classification models. We did hyperparameters tuning to optimzie the models. At the end, we check the performance of each models by comparing the test accruacy scores and found naive bayes multinominal classifier is the best fit to predict the psot categoriy from these two subreddits.  


## Rubric
Your instructors will evaluate your project (for the most part) using the following criteria.  You should make sure that you consider and/or follow most if not all of the considerations/recommendations outlined below **while** working through your project.

For Project 3 the evaluation categories are as follows:<br>
**The Data Science Process**
- Problem Statement
- Data Collection
- Data Cleaning & EDA
- Preprocessing & Modeling
- Evaluation and Conceptual Understanding
- Conclusion and Recommendations

**Organization and Professionalism**
- Organization
- Visualizations
- Python Syntax and Control Flow
- Presentation

**Scores will be out of 30 points based on the 10 categories in the rubric.** <br>
*3 points per section*<br>

| Score | Interpretation |
| --- | --- |
| **0** | *Project fails to meet the minimum requirements for this item.* |
| **1** | *Project meets the minimum requirements for this item, but falls significantly short of portfolio-ready expectations.* |
| **2** | *Project exceeds the minimum requirements for this item, but falls short of portfolio-ready expectations.* |
| **3** | *Project meets or exceeds portfolio-ready expectations; demonstrates a thorough understanding of every outlined consideration.* |


### The Data Science Process

**Problem Statement**
- Is it clear what the goal of the project is?
- What type of model will be developed?
- How will success be evaluated?
- Is the scope of the project appropriate?
- Is it clear who cares about this or why this is important to investigate?
- Does the student consider the audience and the primary and secondary stakeholders?

**Data Collection**
- Was enough data gathered to generate a significant result?
- Was data collected that was useful and relevant to the project?
- Was data collection and storage optimized through custom functions, pipelines, and/or automation?
- Was thought given to the server receiving the requests such as considering number of requests per second?

**Data Cleaning and EDA**
- Are missing values imputed/handled appropriately?
- Are distributions examined and described?
- Are outliers identified and addressed?
- Are appropriate summary statistics provided?
- Are steps taken during data cleaning and EDA framed appropriately?
- Does the student address whether or not they are likely to be able to answer their problem statement with the provided data given what they've discovered during EDA?

**Preprocessing and Modeling**
- Is text data successfully converted to a matrix representation?
- Are methods such as stop words, stemming, and lemmatization explored?
- Does the student properly split and/or sample the data for validation/training purposes?
- Does the student test and evaluate a variety of models to identify a production algorithm (**AT MINIMUM:** two classification models, **BONUS:** try a Naive Bayes)?
- Does the student defend their choice of production model relevant to the data at hand and the problem?
- Does the student explain how the model works and evaluate its performance successes/downfalls?

**Evaluation and Conceptual Understanding**
- Does the student accurately identify and explain the baseline score?
- Does the student select and use metrics relevant to the problem objective?
- Does the student interpret the results of their model for purposes of inference?
- Is domain knowledge demonstrated when interpreting results?
- Does the student provide appropriate interpretation with regards to descriptive and inferential statistics?

**Conclusion and Recommendations**
- Does the student provide appropriate context to connect individual steps back to the overall project?
- Is it clear how the final recommendations were reached?
- Are the conclusions/recommendations clearly stated?
- Does the conclusion answer the original problem statement?
- Does the student address how findings of this research can be applied for the benefit of stakeholders?
- Are future steps to move the project forward identified?


### Organization and Professionalism

**Project Organization**
- Are modules imported correctly (using appropriate aliases)?
- Are data imported/saved using relative paths?
- Does the README provide a good executive summary of the project?
- Is markdown formatting used appropriately to structure notebooks?
- Are there an appropriate amount of comments to support the code?
- Are files & directories organized correctly?
- Are there unnecessary files included?
- Do files and directories have well-structured, appropriate, consistent names?

**Visualizations**
- Are sufficient visualizations provided?
- Do plots accurately demonstrate valid relationships?
- Are plots labeled properly?
- Are plots interpreted appropriately?
- Are plots formatted and scaled appropriately for inclusion in a notebook-based technical report?

**Python Syntax and Control Flow**
- Is care taken to write human readable code?
- Is the code syntactically correct (no runtime errors)?
- Does the code generate desired results (logically correct)?
- Does the code follows general best practices and style guidelines?
- Are Pandas functions used appropriately?
- Are `sklearn` and `NLTK` methods used appropriately?

**Presentation**
- Is the problem statement clearly presented?
- Does a strong narrative run through the presentation building toward a final conclusion?
- Are the conclusions/recommendations clearly stated?
- Is the level of technicality appropriate for the intended audience?
- Is the student substantially over or under time?
- Does the student appropriately pace their presentation?
- Does the student deliver their message with clarity and volume?
- Are appropriate visualizations generated for the intended audience?
- Are visualizations necessary and useful for supporting conclusions/explaining findings?


---

### Why did we choose this project for you?
This project covers three of the biggest concepts we cover in the class: Classification Modeling, Natural Language Processing and Data Wrangling/Acquisition.

Part 1 of the project focuses on **Data wrangling/gathering/acquisition**. This is a very important skill as not all the data you will need will be in clean CSVs or a single table in SQL.  There is a good chance that wherever you land you will have to gather some data from some unstructured/semi-structured sources; when possible, requesting information from an API, but often scraping it because they don't have an API (or it's terribly documented).

Part 2 of the project focuses on **Natural Language Processing** and converting standard text data (like Titles and Comments) into a format that allows us to analyze it and use it in modeling.

Part 3 of the project focuses on **Classification Modeling**.  Given that project 2 was a regression focused problem, we needed to give you a classification focused problem to practice the various models, means of assessment and preprocessing associated with classification.   
