# wassup_proj2nd

- 팀장: 이유성
- 팀원: 강현준, 김정현, 박지연, 윤재현

- ---
## DATA(Time Series)

Enefit - Predict Energy Behavior of Prosumers
</br>
Data Source: https://www.kaggle.com/competitions/predict-energy-behavior-of-prosumers/overview
</br></br>
Prosumer
</br>
Producer + Consumer
</br>
Prosumer란 판매나 교환을 위해서라기보다 자신의 사용이나 만족을 위해 제품, 서비스 또는 경험을 생산하는 사람이며, 개인 또는 집단이 생산하면서 동시에 소비하는 행위를 Prosuming이라고 한다. _ Alvin Toffler(엘빈 토플러, 『제3의 물결』)

**columns**
+ country
+ is_business
+ product_type
+ datetime
+ data_block_id
+ row_id
+ is_consumption
+ prediction_unit_id
+ target: The consumption or production amount for the relevant segment for the hour. The segments are defined by the county, is_business, and product_type

  
**결론**
+ ARIMA 모델을 베이스 모델로 사용하였으나 각 피크 지점을 잘 예측하지 못했다.
+ 피크를 더 잘 예측하기 위해 ANN 모델을 사용하였고, ARIMA 보다 성능은 향상되었지만 여전히 피크 지점을 잘 예측하지 못했다.
+ Residual learning을 적용,  피크 지점 예측이 개선되었다.
+ patchTST 모델의 성능은 ANN보다 낮았다.
+ Residual learning을 patchtst에 적용한 결과 학습 시간이 확연히 줄어들고 모델 성능이 비약적으로 상승했다.
+ 결과적으로 이 실험에서 patchtSRT가 가장 높은 성능을 보였다.

