# Sentimental_Analysis

   - 네이버 영화평을 직접 크롤링하여 평점  진행


           datasets
           ├── 19년 시행착오
           │   ├── Final
           │   └── LSTM
           │   └── US sklearn
           │   └── Vectorization
           │   └── 신의한수 sklearn
           │       
           └── Bert_Classification
               ├── bert_classification.ipynb
               └── best_train.csv
               └── worst_train.csv
## Prerequisites

- Python 3.6+
- Tensorflow
- Sklearn

## Process

### 1. 개요


- - 현재 인스타그램, 배달 앱, 쇼핑 앱 등 모든 정보들이 사람들에 의해 리뷰됨

    비정형 데이터 수집 및 공부 필요<br>
    Beautifulsoup, selenium 라이브러리 활용한 비정형 데이터 수집 독학
    -네이버 영화평을 직접 수집하여, 감정 분석 프로젝트


### 2. Data collection & Data Preprocessing

- 네이버 영화평이 많은 Avengers 영화평 수집

① 영화평 : Document , 별점 : label<br>

        - 별점 5점 이상 : 1 (긍정)
        - 별점 5점 미만 : 0 (부정)<br>


② 데이터 수집 시, 최신 기준 크롤링<br>

        - Training dataset = page 1 ~ page 5000의 리뷰 (50000개)
        - Test dataset = page 5001 ~ 6000의 리뷰 (10000개)
③ Konlpy 패키지, nltk를 이용한 형태소 분석<br>


        - 불필요한 자주 나오는 형태소 제거(조사 등)<br>


④ 자주 사용되는 토큰을 CountVectorization<br>

④ DNN 구조로 모델 구성<br>

        - 입력층, 은닉층 (‘relu’ 함수), 출력층 (‘Sigmoid’ 함수) 구조


### 3. Evaluation

- Test set : tokenizer 후, predict 함수로 예측
  - 확률을 기준으로 0.5 이상 : 1 (긍정) , 0.5 미만 : 0 (부정) 할당
  - Accuracy, Precision, Recall 등 기본 performance 비교

### 4. 시사점 및 개선 방향

- 사람들의 실제 후기에 대한 평점 점수 기준이 각기 상이

- 이상치나 결측치 등을 판단하기가 어려워 분석의 정확도가 낮은 것으로 판단됨
- DNN 모델의 구조 변경 필요
- 데이터 전처리 및 모델링 기법 공부 및 적용 필요
- NLP 논문 학습 필요


## References

- https://cyc1am3n.github.io/2018/11/10/classifying_korean_movie_review.html

## Author

HyoJun Kim / [blog](http://rlagywns0213.github.io/)
