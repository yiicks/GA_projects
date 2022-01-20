### Introduction & Problem Statement
As a Redditor and data aficionado, train a classifier to tell two sub-reddits apart using evaluation metrics (below):
- `r/jobs`, which focuses more on immediate issues and getting a job, and 
- `r/careerguidance`, which focuses more on longer-term (career) decisions.

#### Context
Administrators and moderators for these sub-reddits have a partnership to develop a feature to suggest to users to in which subreddit to post their content. This feature will simply take their content (`selftext`) and evaluate where their post belongs.

There is some active moderation which results in post removals. Moderation policy is less clearly written out for the `r/careerguidance` subreddit.
- [Moderation Policy for r/jobs](https://www.reddit.com/r/jobs/wiki/policy)
- [Modpost for r/careerguidance](https://www.reddit.com/r/careerguidance/comments/fwdma6/new_post_requirement_please_use_location_flairs/)

Caveat: Context is fictional. :)

---

#### Evaluation & metrics
The cost of misclassification is that the feature being developed would misplace the post, meaning more work for moderators. As a classification model, we look at not just accuracy, but also precision and recall. As there is no distinct reason to prioritize either precision or recall, we will focus on the F1 score.

---

### Methodology

#### Scraping
Scape **posts** using Pushshift's API, then use NLP to discern investing advice between two investment-related sub-reddits: 
- [r/jobs](https://www.reddit.com/r/jobs/) and
- [r/careerguidance](https://www.reddit.com/r/careerguidance/).


#### Cleaning and EDA

#### Data
We start with two raw datasets / corpora scraped in the previous notebook of ~2500 posts per subreddit:
1. `r/jobs` and 
2. `r/careerguidance`).

This number of posts was scraped to get >700 unique `selftext` samples per subreddit.

The key variables are:
1. `title`,
2. `subreddit`, and
3. `selftext`.

|Parameter|Type (raw)|Type (cleaned)|Description|
|:-:|:-:|:-:|:--|
|title        |obj|str|title of subreddit post
|selftext     |obj|str|content / text of subreddit post
|subreddit_jobs|n/a|uint8|subreddit the post belongs to; `0` for `r/careerguidance`, `1` for `r/jobs`
|combined_text|n/a|str|created field; concatenation of title and selftext

As we looking to eventually perform some binary classification, we already know that `subreddit` can be transformed into a binary variable (0 or 1).

There are also a few words we should be removing, for example if the subreddit name (and permutations of the acronym) as these have strong predictive power but should not be expected as part of inputs in future predictions.

### Conclusions and Recommendations

**Model selected**: Multinomial Naive Bayes with tf-idf vectorizer

```
Best parameters set:
	nb__alpha: 3
	tvec__max_df: 0.5
	tvec__max_features: None
	tvec__min_df: 0.01
	tvec__ngram_range: (1, 3)
```

We see from the model scores that while random forest classifiers provide high train scores, their validations scores with the test corpus are much lower, meaning they likely over-fit and do not generalize well. They take far longer to tune and run, with an average of 20 minutes.

We select the Multinomial Naive Bayes model with the highest Validation F1 score.
Both Multinomial Naive Bayes models (applying either vectorizer) show much smaller drops in train to validation scores, indicating that they generalize better. On top of that, tuning takes far less time to run (under 3 minutes).

For our use case, we plan to demo this feature within our internal team first, and deploy to production after augmenting with new findings. As such, a lower tuning run time is preferred for now.

#### Further steps
- Preprocessing: iteratively attempt lemmatization and augment stop words
- Review misclassification iteratively and add relevant steps in preprocessing to improve model scores
- Try other models and vectorizers

### Thanks for reading!