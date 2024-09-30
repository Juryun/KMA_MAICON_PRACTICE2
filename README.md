# 국방 AI 경진대회 대비 연습문제2

위 연습문제는 학습데이터, 테스트데이터, 각 문항에 대한 IPYNB 형태의 파일로 이루어져 있습니다. 세 문항 모두 동일한 데이터를 활용하며, 각 문항에 알맞게 코드를 작성하여야 합니다.

# 1. 모델 학습 문제
위 문제에서 활용되는 데이터는 아래 항목과 같이 구성되어 있다.
- restaurant, total_fat, sat_fat, trans_fat, cholesterol, sodium, total_carb, fiber, sugar, protein, calories

데이터의 각 항목들을 활용하여 테스트용 데이터의 칼로리를 예측하여 반환하는 모델을 구현하시오.

제한사항

- None 이외의 미리 주어진 코드를 임의로 수정하는 경우, 정상적인 채점이 어려울 수 있습니다.
- 함수가 지시사항대로 값을 계산하지 않고 특정 값을 반환하도록 하드코딩된 경우 오답으로 처리합니다.
- 주어진 학습데이터 이외의 데이터를 통해 모델을 학습시키면 안됩니다.
- 학습과정에서 테스트 데이터를 통한 학습이 이루어지지 않아야 합니다.

지시사항

1. 데이터 분리
  
   - df_train에는 예측에 사용할 수 있는 여러가지 정보와 y값에 해당하는 calories가 들어있습니다.
   - 이를 모델의 입력값인 x_train와 정답인 y값에 해당하는 y_train로 분리하세요.
      - x_train에는 df_train에서 calories를 제외한 칼럼들이 포함됩니다.
      - y_train에는 df_train의 calories 칼럼만 가져옵니다.

2. 모델 학습
  
   - 학습에 사용할 모델의 정의하여 model에 저장합니다
   - x_train, y_train를 이용해 학습을 진행합니다.

3. 모델 추론 및 결과 반환
  
   - 학습된 모델 model에 df_test를 입력하여 결과를 예측하여 반환합니다.
   - df_tesst의 pred의 내용을 calories 칼럼으로 추가합니다.
   - df_test를 반환합니다
   - df_test의 데이터 순서가 달라질 경우 오답으로 처리될 수 있습니다.

4. 평가 점수
  
   - 제출한 df_test와 실제 정돕을 비교한 MAPE 지표에 따라 점수가 부여됩니다.
   - 점수 : 0.15이하 만점 부여



# 2. 데이터 전처리

지시사항

1. 칼럼 제거하기
  
   - drop_columns 함수를 활용하여 칼럼을 제거하시오.
   - 주어진 데이터프레임 df에서 "vit_a", "vit_c", "calcium" 칼럼을 제거하여 반환하는 함수입니다.
   - 반환 타입은 pd_DataFrame입니다.

2. 결측치 제거하기
  
   - drop_nan 함수를 활용하여 결측치를 제거하시오.
   - 데이터프레임 df에서 결측치가 있는 모든 행을 제거하여 반환하는 함수입니다.
   - 반환 타입은 pd.DataFrame입니다.

3. 레이블 인코딩
  
   - label_encoding 함수를 활용하여 레이블 인코딩을 진행하시오.
   - 전달받은 series의 텍스트 데이터를 unique 함수를 이용해 고유한 숫자형 데이터로 반환하는 함수입니다.
   - 예 : "Arbyb" : 0, "Burger King" : 1 ...
   - 반환 타입은 pd.Series입니다.


# 3. 데이터 시각화

지시사항

1. 데이터 수 구하기
   - get_counts 함수를 작성하시오.
   - 음식점별 데이터 수를 구하시오.
   - df의 "restaurants" 열에서 각 고유한 값들의 개수를 세고, 그 결과를 반환하는 함수입니다.

2. 특정 데이터 추출하기
   - get_fat_foods 함수를 작성하시오.
   - 칼로리가 높고 지방이 많은 음식을 구하시오.
   - df에서 다음 아래 조건을 모두 만족하는 데이터들만 데이터프레임의 형태로 반환하는 함수입니다.
         - calories가 880보다 큼
         - total_fat가 20보다 크거나 같음


3. 히스토그램 그리기
  
   - make_hist 함수를 작성하시오.
   - 인자로 전달받은 df는 train.csv 데이터입니다. 아래 조건을 만족하는 df에서 calories의 히스토그램을 그리시오.
      - matplotlib.pyplot 라이브러리를 이용해야합니다.
      - histtype은 "bar"로 지정해야합니다.
      - 구간은 30개로 나누어 그립니다.

4. 상관계수 히트맵 그리기
  
   - make_hitpmap 함수를 작성하시오.
   - df의 상관관계를 구해 라이브러리를 활용하여 히트맵을 그립니다.