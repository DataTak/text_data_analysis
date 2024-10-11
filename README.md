# 네이버 영화평 데이터 감성 분석

## 프로젝트 개요
한국어 데이터 셋으로 구성된 영화 리뷰 데이터를 사용하여 감성 분석을 진행합니다. 이 프로젝트의 목표는 한국어 데이터 셋을 사용하여 텍스트 분석을 수행하고, LSTM 기반 감성분류기를 학습시켜 새로운 리뷰에 대한 긍정/부정을 판단하는 모델을 생성합니다.

## 데이터 설명
- 데이터 출처: [네이버 영화 리뷰 데이터](https://github.com/e9t/nsmc/)
- 데이터 상세: 150K 리뷰 데이터
    - `id`: id
    - `document`: 리뷰
    - `label`: 긍정(1), 부정(0)
- 참고
    - 영화평 별점 기준 9~10점은 긍정(1), 1~4점은 부정(0)으로 레이블링 된 데이터
    - 5~8점(중립)에 해당하는 데이터는 포함되어 있지 않음
    - 모든 리뷰는 140자 미만 작성됨

## 분석과정
1. EDA
   - 긍정, 부정 리뷰에 대한 WordCloud 생성
   - 리뷰의 글자수에 대한 분포 확인(histplot)
   - 리뷰의 긍정/부정에 대한 비율 확인

2. 데이터 전처리
   - 토큰화(konlpy)
   - 불용어(stopwords) 처리
   - 각 토큰을 벡터로 변환
   - 패딩(pad_sequences)

3. 딥러닝 모델 생성
   - Bi-LSTM 기반 신경망 생성

4. 평가
5. 예측

## 주요 결과 및 성과
- 테스트 셋에 대하여 정확도 81.7%를 만족하는 모델 생성(학습 데이터 기준 정확도 84.2%)


## 필요한 라이브러리
- pandas
- numpy
- matplotlib
- seaborn
- WordCloud
- Counter
- sickit-learn
- TensorFlow
