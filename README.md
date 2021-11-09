# Ryerson-Capstone-course
Research:
Covid-19 related topics and sentiments in english Twitter tweets. Compared at beginning of pandemic (May 2020) and more recently (Sep 201).

Approach for data analysis: to determine a base for data-analysis, I developed a corpus and topic analysis by taking a sample of 1,000 docs/tweets out of the more 2.3 million Covid tweets in the original data set from IEEE. Main reason fro this was to reduce processing and system time, as I run into memory issues on my computer.

Data set uploaded: rawData.csv includes the hydrated tweets data set for May 16, 2020 from IEEE after taking a sample of size 1,000. The original data set of more than 2 million tweets was to large to upload on Github.

Scripts uploaded:

A) Describing data set FINAL. This script that describes the hydrated tweets data set for May 16, 2020 from IEEE. string information is provided including frequency of relevant fields for strata including "coordinates", "place", and "location" (please see paper as part of literature review for more info) as well as graphical presentation of characters in tweets and number of retweets. The data set is further subsetted for tweets that have valid long an lat "coordinates" and for which accurate city names could be retrieved using Photon. The geographical spread of this subset of tweets is graphically presented on a world map. Also is including a list with Top-10 cities i.e. cities from which more than 10 tweets were sent.

B) Word cloud. Shows frequent terms in data set May 2020. These will be compared to frequent terms in data set Sep 2021 as part of module 4 analysis.

C) LDAMay2020 updated FINAL. This is the script from the lab CIND110 module 10. I was not able to effectively execute this script after many tries. 
I encountered the following issues (amongst many others): 

  1) Vcorpus after processing/cleansing is showing unrecognizable uni-gram terms that do not match with any of the terms in the documents. Based on these terms, sparcity is extreemly high and LDA analysis doesn't produce useful differentiation for topics in a doc/tweet querry as a result. So, I doubt that DTM script after data cleansing is correct.
  2) I tried running a corpus with function Corpus() which did produce terms as expected, but function Corpus() has fixed tokenization which doesn't allow to adjust n-gram for terms. As a result, the bigram script produced an error.
  3) I had some success with additional processing/cleaning steps, similar as per word cloud script, but the corpus created an error when reading the cleaned corpus into the DTM script. Somehow, by not using tm::tm but format tm_map(), the corpus was manipulated in a different format. I was able to fix this by running function tm_map(corpus, as.PlainTextDocument). However, this resulted in error when running bigram scripts, again.

Note: I was not able to create a base line and run multiple analysis as a result of the issues with the script i.e. n-gram/3-gram, use additional dictionaries, measure impact on baseline by removing stemming, review heatmap, etc. I have however included my own script below as well (D).  

D) LDA script Josh FINAL. This script was put together from various authors following internet research as my initial focus was on answering the research question. With this script, I achieved better interpretable results on terms, after cleansing, and topic relevance. I was however not successful to include a confusion matrix using the caret packaged as I'm not entirely sure how the LDA results are interpreted and flown through the caret package and generate a confusion matrix.

E) Sensitiment analysis FINAL added graphs, this script provides an analysis of the the May tweets sample data set by determining sentiment scores of tweets based on a dictionar on a scale of positive sentiment rated max 1.0, neutral (-0.25, 0.25) and negative -1.0. 

F) Emoji sentiment analysis FINAL, this script provides a sentiment analysis based on emojis i.e. rank emojis by occurence, tweets with most emojis, number and average of emojis in sample data set, sentiment analysis with emojis by assigning a score to a tweet, emojis associated with words in tweets. 


G) GloVe simple FINAL, this script is a "simple" application of word embeddings with GloVe algorithm via text2vec. Unfortunately the code: "source("helper_functions.R")" can't find the file and doesn't cast/call itself!!! Not sure what is the issue. I cleared-out the Global Environment, but not sure why this is not working for me. I might need some guidance to resolve this issue.


Important Note: the scripts presented concentrate on the May 2020 data set. Once the LDA scripted is "debugged" for bigram DTM in file LDAMAY2020, as described above, the September 2021 dataset can be loaded, processed, and output can be compared. However, I wsn't successful in debugging, as I believe there is an issue with the format the corpus is transformed when pre-processed/cleansed. Reducing the number of pre-processed steps lead to unclear topic latency in teh LDA analysis / graph... I believe further cleansing is needed as the tweet data ($text) is very "sloppy" with all sorts of terms i.e. "http", "&amp", etc.

Important note: I wasn't successful in applying the carnet package to script a confusion matrx to the LDA topic results, so i will need to better understand how to determine precision and recall with a sample size of 1,000 tweets vs 24 docs as per the lab in module 10. 
