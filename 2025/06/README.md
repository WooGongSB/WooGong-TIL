## 2025-06-27
- Machine Learning 내용 정리
- 머신러닝
    - 지도학습
        - Regresion (회귀)
            - 방법론
                - Linear Regression Model (선형 회귀 모델델)
                    - 최소제곱법 : 오차 제곱의 합을 통해 해를 구하는 방법
                    - 입력 변수가 많다고 좋은 것은 아님. 변수가 많아질수록 과적합 (Overfitting) 또는 다중공선성 (Multicollinearity) 과 같은 문제가 발생할 수 있다. 이러한 문제는 회귀 모델뿐만 아니라 인공지능 전 분야에 걸쳐 나타나는 현상. 과적합은 모델을 사용하는 학습데이터를 너무 집중적으로 추정함으로써 실제로 맞추어야 할 데이터에 대해서는 잘 맞지 않는 현상을 의미.
                    - 다중공선성 : 입력변수와 출력간의 높은 상관관계를 갖는 것.
                    - 선형 회귀 모델의 장점 : 설명력
                        -다른 지도학습과 비교했을 때 '예측력'관점에서 우수한 편은 아니지만 출력변수와 입력변수 사이의관계를 쉽게 설명 가능한 선형방정식으로 구명하기 때문에 입력 변수가 출력 변수에 대해 어떻게, 얼마만큼 영향을 주는지 알 수 있다. 이와 반대로, 복잡하고 예측력이 좋은 모델의 경우에는 설명력이 떨어지는 단점이 있다. 방법론을 선택할 때 설명력과 예측력 중 어느 것에 초점을 맞출 것인지 고려해야 한다.
                    1. Logistic Regression Model (로지스틱 회귀 모델)
                        - 출력값이 범주형인 경우 적용할 수 있는 회귀모델 중 하나.
                        - 범주가 3개 이상인 경우에도 적용할 수 있지만 회귀식이 복잡해 지므로 설명력이 장점인 회귀모델의 매력이 줄어들기 때문에 자주 사용하지는 않는다.
                        - Odd : 임의의 사건이 실패할 확률 대비 성공할 확률의 비율.
                        - Sigmoid Function : S 자 곡선의 형태를 보이며, Log Odds 의 형태.
                    2. Lasso, Ridge
                        - 입력 변수가 많으면 과적합과 다중공선성이 발생할 가능성이 커지기 때문에 변수를 줄이거나 변수의 영향도에 적절한 처리를 하는 노력이 필요하다.
                        - 모델링 관점에서 과적합과 다중공선성의 문제를 해결하고 일반화된 모델을 구성하는 기법을 일반화라고 하며 모델의 학습 parameter 를 추정하는 과정에서 Penalty Term 등을 추가하여 모델이 일반화를 도모하는 것을 Regularization(정규화)라고 한다.
                        -회귀모델에 Regularization 을 적용하는 방법론은 Lasso (Least Absolute Shrinkage and Selection Operator) 와 Ridge 라는 두개의 모델이 있다.
                - Decision Tree (의사결정나무)
                - SVM (Support Vector Machine)
                    - Data Class 들을 가장 잘 나눌 수 있는 Decision Boundary (결정 경계)를 정하는 모델
                    - 각 Class 데서 결정 경계와 가장 가까운 데이터를 Support Vector fkrh gkau, 두 Class 사이의 거리를 Margin 이라고 한다.
                    - Margin 을 최대화 하는 결정 경계를 Hyperplane (초평면) 이라고 하며, 이 Hyperplane 을 찾는 것이 SVM 의 목적.
                - K-Nearest Neighbors(K-NN)
                    - 직관적이고 실제 많은 연구에서 높은 예측력을 보여주는 알고리즘
                    - 새로 입력되는 데이터와 기존의 데이터 사이의 거리를 모두 계산하고 비교해야 하므로 데이터가 많을수록 학습속도가 급격하게 느려지는 단점이 있다.
                - Ensemble Model
                    - 여러 모형의 결과를 종합하여 단일 모형보다 정확도를 높이는 방법
                    - "표본 추출 + 모델링" 과정을 여러번 반복하여 진행.
                    - 반복 모델링한 여러 결과값을 회귀에서는 평균, 분류에서는 투표를 통한 다수결로 최종 예측값을 결정.
                    - Ensemble Model 의 대표 방법론
                        - Bagging (Bootstrap Aggregating) : 이미 존재하는 데이터로 부터 같은 크기의 표본을 여러번 복원 추출한 Bootstrap sample 에 대해 예측 모델을 생성한 후 그 결과를 조합하는 방법론
                        - Boosting : Bootstrap 표본을 구성하는 과정에서 이전 모델의 결과에 반영하여 잘못 예측된 데이터의 비율을 높여 더욱 집중적으로 학습하는 방법론.
                        - Random Forest : Bagging 의 일종으로 의사 결정나무가 모여 숲을 이룬 것 같은 형태를 말하며, 각 의사결정나무 모델링 단계에서 변수를 랜덤으로 선택하여 진행하는 방법론
                    - Bagging 과 Random Forest 는 각 반복의 모델링이 독립적으로 진행되지만, Boosting 은 연속적으로 진행.
                    - Boosting 에서는 첫번째 모델링 결과를 반영하여 두번째 모델에 반영하고, 세번째 모델링할 때는 두번째 모델의 결과를 참고한다.

        - Classification (분류)
        - 대부분의 지도학습 모형은 회귀나 분류에 상관없이 모두 적용할 수 있지만, 방봅론 내부의 손실함수(Loss Function)가 다르다는 차이점이 있다.
        - 손실함수(Loss Function) : 학습데이터 n 개에 대한 예측결과와 실제 정답 사이의 차이를 의미하며 얼마나 틀렸는지 채점하는 함수.
            - MSE (Mean Squared Error : 평균 제곱 오차)
            - CEE (Cross Entropy Error : 교차 엔트로피 오차)
        

    - 비지도학습
---
## 2025-06-26
```java
import  java.util.Scanner;

...

Scanner stdIn = new Scanner(System.in);

...

int a = stdIn.nextInt();

System.out.print("...");
System.out.println("...");
```

| Method | Data Type | Value Range |
|------| :------: | ------ |
| nextBoolean() | boolean | true or false |
| nextByte() | byte | -128 ~ 127 |
| nextShort() | short | -32,768 ~ 32,767 |
| nextInt() | int | -2,147,483,648 ~ 2,147,483,647 |
| nextLong() | long | -9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807 |
| nextFloat() | float | 1.40129846432481707e-45 ~ 3.40282346638528860e+38 (positive or negative) |
| nextDouble() | double | 4.94065645841246544e-324d ~ 1.79769313486231570e+308d (positive or negative) |
| next() | String | the entire line until a newline character |
| nextLine() | String | single token (word) |

---
## 2025-06-25
- TIL 시작
- How to Use github multi Account in Windows
    - 블로그 작성 : [https://www.woogong.com/windows-multiple-github-accounts-ssh/](https://www.woogong.com/windows-multiple-github-accounts-ssh/)