# Data-Analysis-Basic
<br>

## Index
- [Wine Quality Prediction](#Wine-Quality-Prediction)
- [Titanic Data Analysis](#Titanic-Data-Analysis)
<br>

# Wine Quality Prediction

## Data
- UCL ML DATA 저장소 - http://archive.ics.uci.edu/ml/machine-learning-databases/wine-quality/
## Description
- red wine과 white wine의 데이터를 하나의 데이터(wine)로 합친다.
- quality 항목을 제외한 나머지 데이터들을 regression 분석을 통해 quality를 예측한다.
- matplot을 이용하여 시각화한다.
<br>

# Titanic Data Analysis

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
