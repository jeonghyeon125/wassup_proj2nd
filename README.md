# wassup_proj2nd

- 팀장: 이유성
- 팀원: 강현준, 김정현, 박지연, 윤재현

## 문서
최종발표 PPT
</br>
https://docs.google.com/presentation/d/1ai5eZ4hEShN-pKnJgVsPzjZPPk3Uf1jtNFkW8j8_gz8/edit

## DATA(Time Series)

**Enefit - Predict Energy Behavior of Prosumers**
</br></br>
Data Source: 
</br>
https://www.kaggle.com/competitions/predict-energy-behavior-of-prosumers/overview
</br></br>
**Prosumer** : Producer + Consumer
</br>
Prosumer란 판매나 교환을 위해서라기보다 자신의 사용이나 만족을 위해 제품, 서비스 또는 경험을 생산하는 사람이며, 개인 또는 집단이 생산하면서 동시에 소비하는 행위를 Prosuming이라고 한다. _ Alvin Toffler(엘빈 토플러, 『제3의 물결』)
</br></br>
**columns**
+ country: int
+ is_business: 0 or 1
+ product_type: int
+ datetime: datetime
+ data_block_id: int
+ row_id: int
+ is_consumption: 0 or 1
+ prediction_unit_id: int
+ target: float
</br>


**preprocessing**
+  생산량과 소비량이 하나의 df에 묶여있으므로 production과 consumption 데이터를 각각의 데이터프레임으로 만든다
+  new_target(production의 target - consumption의 target)을 생성하여 net_target을 예측한다.

## 학습
**사용모델**
+ ARIMA
+ ANN
+ Transformer
</br>


**Metrics**
+ MAPE
+ MAE
+ MSE
+ R2SCORE
</br>


**Results Archive**
https://docs.google.com/spreadsheets/d/1cvwNjQtbZt77MvQrqNSvuSsO2zqvBoulk9GullcgOcY/edit?gid=11555230#gid=11555230
</br></br>


## 결론
+ ARIMA 모델을 베이스 모델로 사용하였으나 각 피크 지점을 잘 예측하지 못했다.
+ 피크를 더 잘 예측하기 위해 ANN 모델을 사용하였고, ARIMA 보다 성능은 향상되었지만 여전히 피크 지점을 잘 예측하지 못했다.
+ Residual learning을 적용,  피크 지점 예측이 개선되었다.
+ patchTST 모델의 성능은 ANN보다 낮았다.
+ Residual learning을 patchtst에 적용한 결과 학습 시간이 확연히 줄어들고 모델 성능이 비약적으로 상승했다.
+ 결과적으로 이 실험에서 patchtSRT가 가장 높은 성능을 보였다.

