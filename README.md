# Domestic-Paper-2
### 발행처: 한국산업정보학회
### 발행날짜: 2019.12
### 제목: 딥러닝을 활용한 자산분배 시스템

### What is the main research question of the study?
   
1) 기존의 딥러닝을 사용한 재무전략은 단일 종목에 대한 주가 예측에만 치중되어 있어 변동성에 취약하다. 따라서 본 연구는 딥러닝을 이용하여 펀드 구성 종목을 산출하고 종목들을 분산투자하여 ETF 상품을 구성하는 모델을 제안한다.
   
### What research methodology did the authors employ?
   
1) 딥러닝의 오토인코더를 사용한다.
   
 인공 신경망을 활용한 ETF 상품을 만드는 포트폴리오 시스템을 제안한다. 오토 인코더를 통해 펀드를 구성할 변수를 선택하고 선택된 변수들을 기존의 금융 포트폴리오 방법을 통 
 해 구매 가능한 펀드를 구성하는 것을 목적으로 한다.  또한 본 시스템은 주가 그래프의 장기적인 움직임을 판단하는 것을 목적으로 하기 때문에 장기 기억에서 기울기 손실 문제 
 가 있는 LSTM 대신 오토인코더 신경망구조를 사용한다.

2) 합성곱 신경망을 이용하여 각 층을 인토딩 2개와 디코딩 2개로 구성하였다. 인코딩 첫번째 층은 16개의 필터, 필터사이즈는 7의 값이다. 2번째 인코더 층은 8개의 필터를 만들며 13의 필터 사이즈를 갖는다. 디코딩층은 인코딩 층과 대칭으로 구성한다. 정규화로 L2를 사용하고 800 EPOCHS를 사용하였다. 활성화 함수로는 RELU를 사용하였다. 손실함수는 MSE를 사용하였다. 옵티마이징 함수는 Adam을 사용했다.

3) 오차값이 가장 작은 상위 15개 종목과 포트폴리오의 기본 속성인 다각화를 위해 오차가 가장 큰 상위 15, 35, 75개를 함께 섞은 포트폴리오를 생성한다.

   
### What were the main findings of the study?

1) 실험 결과로 제안하는 모델을 통해 코스피 100 지수를 대상으로 하는 성능을 분석하며 수익률 또는 안정성 측면에서 향상된 결과를 확인하였다. 즉 딥러닝 기반의 포트폴리오 시스템을 통해 만든 ETF상품과 국내 대표지수 중 하나인 코스피 100과의 비교분석을 통해 설명하려 한다.

2) 평균 수익률 관점에서 성능평가를 하였을 때 평균-분산 포트폴리오 방식이 높은 수익률을 보였다. 샤프비율관점에서는 동일비중 포트폴리오가 높은 성능을 보였다. 최댓값 대비 하락률을 기준으로 보았을 때 시가총액 가중 포트폴리오가 30, 50개 종목을 선택하는 모델에서 가장 높은 성능을 보였다. 

3) 본 실험의 결과 실험 기간의 모든 구간에서 MEAN_VARIANCE 방법론으로 만든 ETF가 좋은 성능을 보였다. 반대로 가장 낮은 샤프비율을 보이며 가장 높은 최댓값 대비 하락률을 보이는 등 변동성이 큰 단점이 존재함을 확인하였다. 또한 동일비중 포트폴리오 및 시가총액 가중 포트폴리오를 통해 만들어진 펀드들은 코스피 100 지수보다 더 높은 샤프비율을 보이고 더 낮은 최댓값 대비 하락률을 보이는 등 변동성이 더 낮은 펀드를 만들 수 있음을 확인하였지만 코스피 100지수에 비해 더 낮은 수익률을 보임을 확인하였다. 

### Did the authors provide appropriate support for their conclusions?

1) 거래일 1054일을 데이터로 사용하였다. 이 중 800 거래일 기준으로 훈련데이터와 데스트 데이터로 사용했으며 훈련데이터 중 마지막 150일은 검증데이터로 사용하였다. 시계열데이터 이기 때문에 섞지는 않았다.

2) 선택된 종목들은 동일비중 포트폴리오, 시가총액 가중 포트폴리오, 평균-분산 포트폴리오 방식을 통해서 ETF 상품으로 만들었다.

3)  결과의 분석을 위해 평균 수익률(기하평균사용), 샤프지수, 최댓값 대비 하락률 지표를 사용하였다.

### What is the significance or importance of this study?

1) 본 논문에서 제안하는 방식은 포트폴리오를 만들경우 더 높은 수익률 혹은 더 적은 변동성을 지닌 펀드를 만들 수 있음을 확인하였다.

### What are the potential limitations of this study?

1) 본 실헝은 기간 변화에 따른 코스피 100 구성 종목 변화에 대응하지 않고 고정된 종목만을 사용한다. 그에 따라 펀드의 구성종목 변화에 대응하는 추가적인 시스템 연구가 필요하다. 

2) 본 연구에서 제안한 실험 모델은 펀드를 구성하는 고정 종목에 대해 각 종목들의 자산구성을 재조정하는 시스템을 고려하지 않았다.
