# Ayotzinpa_Linguistic_Analyses
 NLP pipline to gather and analyze information regarding the events of Ayotzinapa
## Project Background
 Final project for Montclair State University Computational Linguistics program meant to show what I have learned


## Dependencies
Download featurefunctions Script
Download Process Script
requirements.txt

## To get started
Follow [**Disinfonlp_Tutorial**](https://github.com/Novetta/Disinformation_Pipeline/blob/master/Disinfonlp_Tutorial.ipynb) above

## For Project and Data Details
See the Final paper for this project: 


## Featurefunctions script 
Script is meant to speed up NLP work

1. **featurefunctions:** turns Tweets into linguistic features and preprocess

2. **Process:** Preprocesses data again



## Outline of Pipeline
![image of pipeline](https://github.com/Novetta/Disinformation_Pipeline/blob/master/pipeline.png)    

## Main Features
-	**Linguistic feature returns:** Users can get count data for part-of-speech representation in each article, overall sentiment scores (see [VADER](https://github.com/cjhutto/vaderSentiment) model), and article complexity returns (i.e. sentence count, word density).
-	**Predictive text classification:** The resulting dataframe from “Features and Model Classification.ipynb” includes a binary classification for each article of either 0 = “disinformation” or 1 = “verifiable” text.
-	**Probabilities:** The resulting dataframe from “Features and Model Classification.ipynb” includes probability returns for each article (scores closer to 1 = “more likely to be verifiable”, scores closer to 0 = “more likely to be disinformation”).
-	**Text summarization:** We employ the EasySummarizer feature of [AdaptNLP](https://github.com/Novetta/adaptnlp) to create summaries of the classified articles. These can then be used for further analysis of disinformation narratives.
-	**Topic Modeling:** Users can get a breakdown of major topics in their dataset as well as corresponding keywords for each.

## Data Fields:
Column Name | Data Type | Description
------------|-----------|------------
`text`      |str       |Primary input for classification model
`pred_type` |int       |Predicted classification of input text
`pred_probabilities`|float|Probability that a text fits either classification
`dominant_topic`|float|Topic assigned to the article
`topic_percent_contrib`|float|How closely aligned the article is with its assigned topic
`keywords`|str|Associated keywords for a given topic
`noun_count_percent`|float|number of nouns in a given text
`adj_count_percent`|float|number of adjectives in a given text
`adv_count_percent`|float|number of adverbs in a given text
`pro_count_percent`|float|number of pronouns in a given text
`char_count`|float|total characters in a given text
`word_density`|float|average words per sentence
`punctuation_count`|float|punctuation in a given text
`upper_case_word_count`|float|number of uppercase words in a text
`vader_pos`|float|VADER positive score
`vader_neg`|float|VADER negative score
`vader_neu`|float|VADER neutral score
`vader_compound`|float|VADER compound score

## Results
Table 1 (Model statistics on labeled training data)
Model Type | F1| Disinfo Accuracy(%)|False positives(%)
------------|-----------|------------|---------------
`LSTM`      |.89      |88    |12
`Logistic regression` |.77    |74       |24
`Random Forest` |.77    |73       |27
`SVC` |.79    |78       |19

Table 2 (Model statistics on articles from Twitter/"real world" data)
Model Type | F1| Disinfo Accuracy(%)|False positives(%)
------------|-----------|------------|---------------
`LSTM`      |.65      |89    |52
`Logistic regression` |.62    |63       |49
`Random Forest` |.56    |52       |39
`SVC` |.56    |57       |53

## Maintenance
We expect topic drift to have an impact on this model’s ability to classify text accurately. For news articles in particular, the rise of sudden new events (like the spread of COVID-19 or the announcement of election results) may result in the model producing more false positives than is desirable. To mitigate this effect, we recommend retraining the model every few weeks by incorporating a new set of labeled texts into the training data we provide. 



