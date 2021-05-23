# Ayotzinpa_Linguistic_Analyses
 NLP pipline to gather and analyze information regarding the events of Ayotzinapa
## Project Background
 Final project for Montclair State University Computational Linguistics program meant to show what I have learned


## Dependencies
Download featurefunctions Script
Download Process Script
requirements.txt

## To get started
Follow [**Full_process*](https://github.com/cmartin009/Ayotzinpa_Linguistic_Analyses/Full_Process.ipynb) above

## For Project and Data Details
See the Final paper for this project: 


## Featurefunctions script 
Script is meant to speed up NLP work

1. **featurefunctions:** turns Tweets into linguistic features and preprocess

2. **Process:** Preprocesses data again



## Outline of Pipeline
![image of pipeline](https://github.com/cmartin009/Ayotzinpa_Linguistic_Analyses/blob/pipeline.png)    


## Main Features
-	**Ayotzinapa Twitter Dataset:** Users gain access to a Twitter Dataset that covers topics surrounding Ayotzinapa from August 2014 to December 2015.Users also gain access to web scraper and Methodology used to collect Ayotzinapa tweets.
-	**Linguistic feature returns:** Users can get count data for part-of-speech representation in each Tweet, overall sentiment scores (see [VADER](https://github.com/cjhutto/vaderSentiment) model), and article complexity returns (i.e. sentence count, word density).
-	**Topic Modeling:** Users can get a breakdown of major topics in their dataset as well as corresponding keywords for each.
-	**Ayotzinapa Timeline:** Users get list of carefully curated events surrounding Ayotzinapa that can be studied further to see if there is any correlation between the linguist feature data and real life happenings.
-	**Data:** All of the resulting data can be put through data visualization software to see if there are any patters.



## Data Fields:
Column Name | Data Type | Description
------------|-----------|------------
`text`      |str       |Primary input for classification model
`dominant_topic`|float|Topic assigned to the Tweet
`topic_percent_contrib`|float|How closely aligned the Tweet is with its assigned topic
`keywords`|str|Associated keywords for a given topic
`noun_count_percent`|float|number of nouns in a given text
`adj_count_percent`|float|number of adjectives in a given text
`adv_count_percent`|float|number of adverbs in a given text
`pro_count_percent`|float|number of pronouns in a given text
`char_count`|float|total characters in a given text
`word_density`|float|average words per sentence
`punctuation_count`|float|punctuation in a given text
`upper_case_word_count`|float|number of uppercase words in a text
`Sentiment`|float|Sentiment score between 1 and 0

