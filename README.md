# DACON 
데이터·AI를 활용한 물가 예측 경진대회 : 농산물 가격을 중심으로

https://dacon.io/competitions/official/236381/overview/description

| **날짜** | **작업** | **인사이트** | **최종 성능(NMAE)** |
|:---:|:---:|:---:|:---:|
| 1 | 데이터 탐색 | 3개의 데이터셋 / 예측 품목마다 차이 존재 / 결측치는 존재하지 않으며 가격 데이터 특성상 0이 결측치로 추정됨 | 미제출 |
| 2 | BaseLine코드 제출 | 전처리 수행X , lstm 기본 모델 성능 확인 | 0.4385 |
| 3 | 데이터 전처리 | 시계열 데이터 특성상 bfill, ffill로 채우는 것이 유용할 것으로 예상하였으나 성능 하락 | 0.5018 |
| 4 | 전처리 및 모델링 | 변수 간의 상관성을 이용, 결측치 대체 & lstm의 layer 3겹 | 0.4714 |
| 5 | - | *전처리 수행을 거듭할수록 성능이 하락하는 현상에 대해 고민 | - |
| 6 | 모델 교체 | lstm에서 transformer 모델로 교체, 약간의 성능 향상 | 0.4178 |
| 7 | 전처리 방식 교체 & lstm | **test 데이터에서도 결측치로 추정되는 0값 발견, train과 동일한 방법으로 처리하는 코드 추가, 눈에 띄는 성능 향상 | 0.3276 |
| - | 전처리 방식 교체 & transformer | **현재 전처리 방식 : 총반입량 0이하 데이터 제거 / 평년평균가격 0인 값을 평균가격으로 대체 | 0.2648 |
| 8 | 데이터 전처리 | *bfill, ffill을 마지막에 적용하여 모든 값 채움, 성능하락 | 0.3277 |
| - | split_time_series | *시계열 데이터 특성을 반영, split_time_series를 통한 데이터 분할 / 처음 전처리 방식을 적용하면 성능 향상 예상 | 0.2997 |
| 9 | 차분 | *가격 데이터에 차분을 적용 / 높은 성능 향상 | 0.1244 |
| 10 | 데이터 전처리 | 전처리 로직 보완, 평균가격을 먼저 채우고 평균가격을 통해 다른 가격 변수 전처리 | 0.1244 |
| 11 | 모델 교체 | transformer 모델의 문제점 발견 / tft, lgbm, gru 모델링 수행, gru로 진행 예정 | 0.1244 |
| 12 | 파생 변수 | 전처리 로직 보완, rolling을 통해 데이터를 채우고 bfill, ffill 순차 적용 | 0.1265 |
| 13 | 모델링 보완 | gru의 하이퍼 파라미터를 수정 | 0.1186 |
| 14 | | | |
| 15 | | | |
