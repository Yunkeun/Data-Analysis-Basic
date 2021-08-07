# Data-Analysis-Basic
<br>

## Index
- [Wine Quality Prediction](#Wine-Quality-Prediction)
- [Titanic Data Analysis](#Titanic-Data-Analysis)
- [Text Sentiment Classification](#Text-Sentiment-Classification)
<br>

# Wine Quality Prediction (2021.04)
## Data
- UCL ML DATA 저장소 - http://archive.ics.uci.edu/ml/machine-learning-databases/wine-quality/
## Description
- red wine과 white wine의 데이터를 하나의 데이터(wine)로 합친다.
- quality 항목을 제외한 나머지 데이터들을 regression 분석을 통해 quality를 예측한다.
- matplot을 이용하여 시각화한다.
<br>

# Titanic Data Analysis (2020.05)
## Data
- seaborn dataset
## Description
- 결측치가 많은 deck는 분석 대상에서 제외한다.
- age의 경우 결측치를 평균값으로 대체한다.
- 생존율 분석 대상
  1. 티켓 등급별 생존율 분석 (pclass)
  2. 같이 탑승한 부모님 또는 어린이 인원수에 따른 생존율 분석 (parch)
  3. 나이에 따른 생존율 분석 (age)
  4. 혼자인 남여의 생존율 분석 (alone, sex)
  5. 선실 등급과 나이에 따른 생존율 분석 (class, age)

## Result
1. pclass
  - 등급의 따른 생존율
    -  1등급 : 약 63.0%
    -  2등급 : 약 47.3%
    -  3등급 : 약 24.2%
  -  티켓 등급이 높을수록(3등급 < 2등급 < 1등급) 생존율이 높아진다는 것을 알 수 있다. 
<br>

2. parch
  - 전체 승객의 약 76.1%는 parch없이 온 승객이다.
  - parch 수가 0인 승객은 전체 승객에 대해 사망 비율이 약 49.9%로 parch 수가 0의 생존 비율인 26.2%에 비해 약 1.9배 높은 사망율을 기록했다.
  - parch 수가 True, 즉 1이상인 승객은 전체의 약 24%로 이들에 대한 사망율과 생존율은 거의 차이가 없다.
<br>

3. age
  - 승객의 연령대는 20대가 가장 많고 그 다음은 30대이다.
  - 0-10세의 아이의 생존율이 약 61.3%로 절반 이상이다. 이것을 통해 아이들을 먼저 구하고자 하는 승객들의 따듯한 마음이 전해진다.
  - 60대 이상의 노인의 생존율이 약 26.9%로 가장 적은 수치를 보인다.
  - 그 다음 낮은 수치가 20대의 생존율이다. 이것 역시 특이한 수치이다.
<br>

4. alone, sex
  - 전체 승객에 대하여 not alone인 경우 생존율과 사망율이 거의 비슷하다.
  - not alone인 승객에 대하여 여성의 생존율은 약 71.3% 이지만, 남성의 생존율은 약 27.1%이다.
  - 전체 승객에 대하여 alone인 경우 사망율이 생존율보다 두 배 이상 높다.
  - alone인 승객에 대하여 여성의 생존율은 약 78.6% 이지만, 남성의 생존율은 약 15.6%이다.
  - 즉, 여성의 경우 alone과 not alone에 크게 상관 없이 생존율이 높지만, 남성의 경우 둘 다 생존율이 낮지만, alone의 경우 크게 낮은 생존율을 보인다.
<br>

5. : class, age
  - 0-10세는 First class와 Second class에서 높은 생존율을 보인다. 하지만, Third class에서는 사망률이 0.4% 더 높다.
  - elder는 class에 상관없이 사망률이 생존율에 비해 두 배에서 세 배 높다.
  - First class에서 elder를 제외한 전 연령층은 생존율이 사망률보다 높다.
  - Third class에서 전 연령층은 사망률이 생존율보다 높다.


# Text-Sentiment-Classification (2021.7)
## 2021 Brno Team Project - Team no.03 <br>
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

