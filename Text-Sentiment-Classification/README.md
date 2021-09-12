# Text-Sentiment-Classifiaction
## 2021 Brno Team Project - Team no.03 

<br>

## Outline
 To utilize the Text Sentiment Classification, an analysis of movie review data (evaluation score + content of evaluation) is conducted. The movie reviews are classified into 5 categories (very negative, negative, neutral, positive, and very positive) and compared to the score (0-5.) and analyzed. This aims to predict scores by creating an emotional classification prediction model. The dataset used Stanford Sentiment Treebank (SST-5). SST-5 consists of 11,855 sentences extracted from movie reviews with fine-grained sentiment labels [1–5], as well as 215,154 phrases that compose each sentence in the dataset.
<br>

## Model Description
1. Text Pre-Processing
To extract only words from the loaded data, we do pre-process. First of all, a non-alphabetic character is converted to a space and a capital letter is converted to a lowercase character. Then use stopwords modules to remove the terminology that does not mean much to the analysis. After that, use the nltk module to perform stemming. The stem is vectorized using CountVector techniques. Then apply TF-IDF to find out the importance of the word.
2. Classification Prediction
Ordinal Logistic Regression was used as an algorithm for classification prediction of evaluation scores as variables. Although it is categorical data like evaluation scores, we used polynomial logistic regression because we had to judge five-step categories, not just positive/negative.
<br>

## Model Evaluation
1. The Confusion Matrix
The results are indicated by the confusion matrix, accuracy scores and f1 scores. The accuracy is 0.40 and the F1 score is 0.33. <br>

![image](https://user-images.githubusercontent.com/70425484/126782067-fca87499-25af-4b2f-908b-3e95b8acf9c4.png) <br> 
When we checked the evaluation score as shown on the left, the number of sentences that succeeded in predicting was not balanced because there were a lot of ratings of 2 and 4. Therefore, based on 1,092 as the smallest number of data (1), 1,000 data are randomly selected and re-trained.
2. Accuracy Supplementation
<br>

![image](https://user-images.githubusercontent.com/70425484/126782151-0225cffb-dfd2-4960-b624-1488b4781d8e.png) 
<br> 
Closer to the ideal graph (darkened in the direction of the inverse diagonal), but less accurate. The accuracy is 0.37 and the F1 score is 0.37. <br>

We assume that the reason for this is that we have reduced the amount of training data. Because the F1 score has risen on that basis. So, if we balance the amount of data that a model trains, we expect it would be a better model.

