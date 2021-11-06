# Ryerson-Capstone-course
Research:
Covid-19 related topics and sentiments in english Twitter tweets. Compared at beginning of pandemic (May 2020) and more recently (Sep 201).

Approach for data analysis: to determine a base for data-analysis, I developed a corpus and topic analysis by taking a sample of 1,000 docs/tweets out of the more 2.3 million Covid tweets in the original data set from IEEE. Main reason fro this was to reduce processing and system time, as I run into memory issues on my computer.

Scripts uploaded:

Word cloud. shows frequent terms in data set May 2020. These will be compared to frequent terms in data set Sep 2021 as part of module 4 analysis.

LDAMay2020 updated FINAL, this is the script from the lab CIND110 module 10. I was not able to effectively execute this script after many tries. 
I encountered the following issues (amongst many others): 
1) Vcorpus after processing/cleansing is showing unrecognizable uni-gram terms that do not match with any of the terms in the documents. Based on these terms, sparcity is extreemly high and LDA analysis doesn't produce useful differentiation for topics in a doc/tweet querry as a result. So, I doubt that DTM script after data cleansing is correct.
2) I tried running a corpus with function Corpus() which did produce terms as expected, but function Corpus() has fixed tokenization which doesn't allow to adjust n-gram for terms. As a result, the bigram script produced an error.
3) I had some success with additional processing/cleaning steps, similar as per word cloud script, but the corpus created an error when reading the cleaned corpus into the DTM script. Somehow by not using tm::tm but format tm_map(), the corpus is manipulated in a different format. I was able to fix this by running function tm_map(corpus, as.PlainTextDocument). However, this resulted in error when running bigram scripts.





