### Project Summary

Step 1) Collect Twitter data on a certain product(s), namely games and

  1a) perform sentiment analysis and aim for good accuracy in correctly identifying the different sentiments
  
  1b) get other metrics such as number of tweets, retweets, view counts etc.


Step 2) Try to see if any variables relate to registrations, engagement, sales in the product domain

- Product of focus (currently): DawnGate and SimCity (this might change or diversify as I make progress in the project)
- Limit the countries to English-speaking countries


### Goal of the Project (general & personal):

- To see if I can find a good way of categorizing tweets accurately. A generic method on tweet texts will allow us to scale up and apply the same methods to text in other platforms (such as other social media, forums, review websites etc.)
- Learn how to use the NLTK library in Python and relevant classification methods
- Learn how to interact with Python to collect web data and work with APIs made available by the popular web platforms
- This is meant to be more of a proof-of-concept; if it works, I am planning to take this back to the company and implement it as a regular/automated report for the internal customers to consume. Even pinning the first part down and turning it into a trackable tool would be quite valuable IMHO. 


### Methods:

#### For Step 1:
- Use NLTK in Python 
	- Train classifiers on certain dataset and test the tweets to see how much accuracy we get
		- I can use Decision Trees, Naive-Bayes or Maximum Entropy classifiers. I am planning to start with Naive-Bayes since that seems to be the most straight-forward for now.
- Count positive/negative words

See how these two approaches perform compared to each other. One thing to note here is that even humans do not always agree on the sentiment class of a text... 

#### For Step 2:
- Regression to tie the twitter data (sentiment/other variables) with variability in registrations, engagement and sales 

### Dataset(s) Description/Sources

- For tweets, I am using Twitter's API (I am still working on getting tweets using Python)
- For a list of positive/negative words, I am using a publicly available list: http://www.cs.uic.edu/~liub/FBS/sentiment-analysis.html#lexicon
- To train my classifiers, I am going to try to use:
	- A movie review sentiment database: http://www.cs.cornell.edu/people/pabo/movie-review-data/
	- I might read a few hundred tweets and classify them accordingly to improve my accuracy
	- Apparently, there are some corpus data that NLTK itself provides (book reviews)
- Registration, activity, sales data will be internal data (not provided here)

### Possible extensions (time permitting):
- Identify influencers within Twitter for the gaming industry
- Gather data on other products and see how they compare
- Other sources for sentiment might be obtained via entertainment review websites (e.g. MetaCritic), message boards (e.g. Reddit) for game related posts. I think this is quite important because Twitter is only a limited source of data and once we include other sources of data, we might end up with a much more complete picture.
- Introduce other/more nuanced classes of sentiment 
	- example to other classes might be as follows: joy, sadness, frustration etc.
	- example to more nuances might be a scale of positivity/negativity like 1-5 (as opposed to having three levels: pos, neg, neutral)
- Try different classifiers than the Naive-Bayes classifier, try different feature selection methods

### Limitations & Notes:
- Twitter has limits on the timeframe I can pull data from and number of tweets
- Staying within single product domain would probably produce the most accurate results
- Additional point: 
> "Python provides an excellent environment for performing basic text processing and feature extraction. However, it is not able to perform the numerically intensive calculations required by machine learning methods nearly as quickly as lower-level languages such as C. Thus, if you attempt to use the pure-Python machine learning implementations (such as nltk.NaiveBayesClassifier) on large datasets, you may find that the learning algorithm takes an unreasonable amount of time and memory to complete.                                                                                                                                                                             If you plan to train classifiers with large amounts of training data or a large number of features, we recommend that you explore NLTK's facilities for interfacing with external machine learning packages. Once these packages have been installed, NLTK can transparently invoke them (via system calls) to train classifier models significantly faster than the pure-Python classifier implementations. See the NLTK webpage for a list of recommended machine learning packages that are supported by NLTK"
> Source: http://nltk.googlecode.com/svn/trunk/doc/book/ch06.html#document-classification


### Bunch of sources on Twitter sentiment:

- http://blogs.ischool.berkeley.edu/i290-abdt-s12/
- https://sites.google.com/site/miningtwitter/questions/sentiment/analysis
- http://www.slideshare.net/ajayohri/twitter-analysis-by-kaify-rais
- http://txcdk.unt.edu/iralab/sentiment_analysis
- http://www.laurentluce.com/posts/twitter-sentiment-analysis-using-python-and-nltk/


- http://text-processing.com/demo/sentiment/
- http://www.sjwhitworth.com/sentiment-analysis-in-python-using-nltk/
- http://andybromberg.com/sentiment-analysis-python/
- http://www.ibm.com/developerworks/linux/library/l-cpnltk/index.html?ca=drs-
- http://www.sananalytics.com/lab/twitter-sentiment/
- http://www.nltk.org/

- https://github.com/japerk/nltk-trainer
- http://breakthroughanalysis.com/2012/01/08/what-are-the-most-powerful-open-source-sentiment-analysis-tools/
- http://nlp.stanford.edu/sentiment/
- http://blog.datumbox.com/how-to-build-your-own-twitter-sentiment-analysis-tool/
- http://www.csc.ncsu.edu/faculty/healey/tweet_viz/tweet_app/