# Industry Classification Project

## What is it?

Brought to you by Fama and Open Avenues Foundation, this project aims to teach the basics and fundamentals of Natural Language Processing (NLP).
Given a dataset of around 20,000 different companies and 13 different classifications of a industry. 
Our aim is to use basic topic classification, unsupervised sentence classification, and vectorization of words to classify the companies to a specific industry.

## Designing the models

Before implementing any of the NLP models, we first created a preprocessor that would clean up the descriptions of the employers and the descriptions of the industry 
to get rid of unnecessary words and random characters that would just create extra "noise" when applying our models to them.
In the preprocessor, we created regex that would find unnecessary patterns and words like email address, phone numbers, emojis, etc.
Cleaning up the data just declutters the dataset a little bit so the models can perform more efficiently and only provide the necessary words that would actually help classify a company.

Computers can not simple process and compute on letters and words to determine relationships between them, so after cleaning up the data we use a 
vectorizer, in our case the TF-IDF vectorizer, to turn the words in the descriptions into vectors. TF-IDF statistically measures and evalutes 
how relevant each word is compared to the whole corpus. Doing this declutters our data even further and just take the most relavent features/words
in the corpus and be able feed our data into our models. 

### Latent Dirichlet Allocation (LDA) Model

The main premise of the LDA model is that it computes onto the given data, in our case the vectorized forms of the company descriptions,
and gives it a score which is the probability that the given words belongs to a specific topic. 

For our case, we applied the LDA model onto both the industry data and then the company data. 
Then after that, for each of the companies, we looped through the industry scores/topics and found which industry that company seems closest to.

This model gave us satisfactory results that, for the most part, gave us accurate results given that some of the companies could have fallen 
onto 2 or more different industries.

### Word Embeddings: Word Vectorization technique

As for the Word Embeddings technique, not only does it take into account the relevance of the words in terms of statistics, 
it also takes into account the meaning of the words. This gives it a huge advantage compares to LDA because now, not only does it
compute the probability of a word being relavent relative to the document, but it takes into account meanings of words and allows 
words that have the same meaning to be represented in similar ways.

For our case we applied the Word Embeddings technique to both the industry data and the companies data. Once we get the vectorized scores of each,
we compared each of the industry vectors to each industry vector to see which industry the company is most similar to,

Similar to the LDA model, the results using the Word Embeddings technique was very promising. It gave us pretty accurate results with only some companies
being classified to an industry that was complete off, i.e a sushi restaurant being classified as education.

## What I learned?

- Data science techniques
- Cleaning up dataset using regex and other string manipulations
- Create a preprocessor that would preprocess the dataset before applying a model
- K-means clustering
- Latent Dirichlet Allocation model
- Word Embeddings technique
- Which technique/model is appropriate for a given problem


## Final Thoughts

We knew right from the bat that our results were not going to be 100% accurate, mainly because of our limited knowledge in machine learning and 
NLP in general. But also, given our very limited time with this whole project, we spent a majority of it actually having to do research and learn
more about each of the models and techniques we needed to implement and then use the remaining sparse time trying to implement the techniques. Adding
to that this project sat in the middle of the semester of school.

With that being said, I learned a whole lot given the 4 weeks we had to complete this project. Most importantly, in my opinion, I understood the basics
of the techniques and models and can actually think of ways to try and optimize them to maybe perform better to what we have currently. For one, I know that
we did not clean the data as well as we could have made it because there were still random 2-3 letter words, words in different languages, and multiple
words which fused together that made no sense at all for the models. But all in all, I am satisfied with what I have produced given all the factors 
I have stated. This project just gave me more interest into the machine learning and AI field that I wouldn't have otherwise.

