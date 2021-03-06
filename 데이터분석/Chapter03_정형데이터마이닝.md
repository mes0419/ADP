<<<<<<< HEAD
## 정형 데이터 마이닝
### 데이터 마이닝 개요
* 데이터 마이닝의 6가지 기능
  * 분류(Classification)
  * 추정(Estimation)  : 연속된 변수의 값을 추정하는데 사용
  ex) 가족 구성원의 총 수입, 고객의 평생 가치 등..
  * 예측(Prediction) : 장바구니 분석
  * 연관 분석(Association Analysis)
  * 군집(Clustering)
  * 기술(Description)
* 데이터 마이닝 기능을 추진하기 위한 5단계
  * 목적 정의
  * 데이터 준비
  * 데이터 가공
  * 데이터 마이닝 기법의 적용
    * 목적 정의 단계에서 데이터 마이닝 기법을 결정하는 것이 좋음
  * 검증

### 분류 분석
* 많이 사용되는 분류 모형
  * 로지스틱회귀, 신경망, 의사결정나무, 앙상블, 규칙기반, 사례기반, 인접이웃, 베이즈, SVM, 유전자 알고리즘 등

#### 로지스틱 회귀모형
* 모형의 적합을 통해 추정된 확률를 사후 확률이라 부르기도 함
* 오즈(odds)의 관점에서 해석될 수 있다는 장점을 가짐
* exp(B1) 의 의미는 x1이 한단계 증가할 때 마다 성공(Y=1)의 오즈가 몇 배 증가하는지를 나타내는 값
* 로지스틱회귀가 분류의 목적으로 사용될 경우에는 Pi(x) 가 기준값 보다 크면 Y = 1 인 집단으로, 작으면
*  Y = 0인 집단으로 분류하게 됨
* 분류기준값의 결정은 정분류율, 민감도, 특이도를 동시에 고려하는 등의 다양한 방법이 사용됨
*

#### 신경망 모형
* 입력층이 직접 출력층에 연결되는 단층신경망(퍼셉트론이라고 불리기도 함)
* z = w'x + w0
* z값에 대해 활성함수가 적용되어 y(x)가 계산됨
* 이 시스템에서 가중치 w는 의사결정 경계(decision boundary)의 방향을 나타내는 모수
* Wo는 의사결정 경계의 위치를 결정하는 모수
* 가중치 W와 Wo는 오차제곱합이 최소가 되는 방향으로 갱신됨
* 최종 목표값 y는 z에 대해 비선형 활성함수 파이(')를 적용하여 구해짐
* 많이 사용되는 활성화 함수
  * 부호(sign) 또는 threshold 함수 : 결과는 -1 또는 1
  * 계단(step) 함수 : 결과는 이진형 0, 1
  * 시그모이드 함수 : 결과는 연속형이며, 0 <= y < = 1
  * SoftMax 함수 : 표준화지수(일반화로지스틱) 함수로도 불리며, 출력값 z가 여러 개로 주어지고, 목표치가 다범주인 경우 각 범주에 속할 사후 확률을 제공
  * tanh 함수 : 결과는 연속형이며, -1 <= y <= 1
  * 가우스 함수 : 결과는 연속형이며, 0 <= y <= 1

#### 다층 신경망
* 여러개의 은닉층(hidden layer)를 가지는 신경망 구조
* 다층신경망의 가중치는 학습과정에서 오차의 역전파 알고리즘을 통해 갱신됨
* 은닉층의 수는 의사결정 경계를 정하는데 중요
* 은닉층의 수를 정할 때는 다음의 사항을 고려함
  * 다층신경망은 훈련이 어렵
  * 시그모이드 활성함수를 가지는 2개 층의 네트워크는 임의의 의사결정 경계를 모형화 할 수 있음
* 각 층의 노드 수의 결정은 다음을 고려하여 결정
  * 출력층 노드의 수는 출력 범주의 수로 결정
  * 입력의 수는 입력 차원의 수로 결정
  *  은닉층 노드의 수는 너무 적으면 복잡한 의사결정 경계를 만들 수 없고, 너무 많으면 네트워크 일반화가 어려움

* 신경망 모형의 장점
  * 변수의 수가 많거나 입, 출력 변수 간의 복잡한 비선형 관계가 존재하는 경우 유용
  * 잡음에 대해서도 민감하게 반응 X
* 신경망 모형의 단점
  * 결과 해석이 어려움
  * 모형이 복잡하면 훈련과정에 시간이 많이 소요   

#### 의사결정나무 모형  
* 상위노드에서의 분류변수, 분류기준값은 이 기준에 의해 분기되는 하위노드에서 노드 내에서는 동질성이 노드 사이에서는 이질성이 가장 커지도록 선택
* 나무 모형의 크기는 과대적합 되지 않도록 합리적 기준에 의해 적당히 조절되어야 함
* 더 이상 분기되지 않는 노드를 최종 마디(terminal node) 라고 함
* 가지분할(split)은 나무의 가지를 생성하는 과정을, 가지치기(pruning)은 생성된 가지를 잘라내어 모형을 단순화하는 과정을 말함
* 목표변수가 이산형인 경우 분류기준값 종류
  * 카이제곱 통계량의 p-값
  * 지니 지수
  * 엔트로피 지수  
* p-값은 그 값이 작을 수록 자식노드 내의 이질성이 큼을 의미
* 지니 지수나 엔트로피 지수는 그 값이 클수록 자식노드 내의 이질성이 큼을 의미
* 목표변수가 연속형인 경우 분류기준값 종류
  * F-통계량의 p-값
  * 분산의 감소량
* p-값이 작아지는 방향으로 가지분할 수행.  
분산의 감소량(variance reduction)은 커지는 방향으로 가지분할 수행
* 의사결정나무의 분석과정
  * 목표변수와 관계가 있는 설명변수들의 선택
  * 분석목적과 자료의 구조에 따라 적절한 분리기준과 정지규칙을 정하여 의사결정나무 생성
  * 부적절한 나뭇가지는 제거
  * 이익, 위험, 비용 등을 고려하여 모형 평가
  * 분류 및 예측
* 의사결정나무분석을 위한 알고리즘 : CHAID, CART, ID3, C4.5, C5.0 등
* 주요 알고리즘 vs 분류 기준변수의 선택법
  * CHAID : 카이제곱 통계량, ANOVA F-통계량
  * CART : 지니지수, 분산감소량
  * C4.5 : 엔트로피지수

* 의사결정나무의 장점
  * 구조가 단순하여 해석이 용이
  * 유용한 입력변수의 파악과 예측변수간의 상호작용 및 비선형성을 고려하여 분석이 수행
  * 선형성, 정규성, 등분산성 등의 수학적 가정이 불필요한 비모수적 모형
* 의사결정나무의 단점
  * 분류기준값의 경계선 근방의 자료값에 대해서는 오차가 큼
  * 로지스틱회귀와 같이 각 예측변수의 효과를 파악하기 어려움
  * 새로운 자료에 대한 예측이 불안정할 수 있음

#### 앙상블 모형
* 여러 개의 분류모형에 대한 결과를 종합하여 분류의 정확도를 높이는 방법
* 적절한 표본추출법으로 데이터에서 여러 개의 훈련용 데이터 집합을 만들어 각 데이터 집합에서 하나의 분류기를 만들어 앙상블하는 방법
* 데이터 조절 방법 : bagging, boosting
* randomForest 모형은 배깅의 기념과 feature의 임의선택을 결합한 앙상블 기법   

##### 베깅
* 배깅은 bootstrap aggregating의 준말로, 원 데이터 집합에서 크기가 같은 표본을 여러번 단순 임의 복원추출하여 각 표본에 대해 분류기를 생성한 후 그 결과를 앙상블하는 방법

##### 부스팅
* 배깅의 과정과 유사하나 붓스트랩 표본을 구성하는 재표본(re-sampling) 과정에서 각 자료에 동일한 확률을 부여하는 것이 아니라,  분류가 잘못된 데이터에 더 큰 가중을 두어 표본 추출
* 아다부스팅(AdaBoosting : adaptive boosting)은 가장 많이 사용되는 부스팅 알고리즘

##### 랜덤포레스트
* 배깅에 랜덤 과정을 추가한 방법
*  부트스트랩 방식에서 예측변수를 임의로 추출하고, 추출된 변수 내에서 최적의 분할을 만들어 나가는 방식
* 새로운 자료에 대한 예측은 분류는 다수결로, 회귀의 경우에는 평균을 취하는 방법으로 사용

#### 모형평가
* 모형평가의 기준은 크게 일반화의 가능성, 효율성, 예측과 분류의 정확성으로 구분
  * 일반화의 가능성 : 같은 모집단 내에 다른 데이터에 적용하는 경우에도 안정적인 결과를 제공하는 것을 의미
  * 효율성 : 분류 분석 모형이 얼마나 효과적으로 구축되었는지 평가  
  적은 입력변수를 필요로 할수록 효율성이 높다고 할 수 있음
  * 예측과 분류의 정확성 : 구축된 모형의 정확성 측면에서 평가하는 것
  * test data를 추출함으로써 2종 오류의 발생을 방지. 이 단계를 위하여 사용되는 추출 방법은 hold-out, cross-validation, bootstrap 방법 등이 존재
    * hold-out : raw data에서 Training/Test data로 구분하는 것
    * cross-validation
    * bootstrap : cv와 유사하나 복원 추출한다는 점에서 차이가 있음. 데이터의 수가 적을 때 많이 활용
* 분류 모형 평가에는 오분류표, ROC 그래프, 이익 도표, 향상도 곡선 등이 존재

##### 오분류표(confusion matrix)
* TP(True Positive) : 실제값과 예측치 모두 True인 경우
* TN(True Negative) : 실제값과 예측치 모두 Fasle인 빈도
* FP(False Positive) : 실제값은 False 이나 True로 예측한 빈도
* FN(False Negative) : 실제값은 True 이나 False로 예측한 빈도

* 정분류율 : TP + TN / P + N, 범주의 분포가 균형을 이룰 때 효과적임
* 오분류율 : FP + FN / P + N,
* 민감도(Sensitivity) : TP / P : 실제값이 True인 관측치중  예측치가 적중한 정도
* 특이도(specificity) : TN / N : 실제값이 False인 관측치중 예측치가 적중한 정도
* 정확도(precision) : TP / TP  + FP = True로 예측한 관측치 중 실제로 True인 비율
* 재현율(recall) : 실제값이 True인 관측치 중 예측치가 적중한 정도. (민감도와 동일 지표)
* F1 = 2 x 정확도 x 재현율 / 정확도 + 재현율
* F(beta) =  (1 + beta^2 ) x Precision x Recall / beta ^  2 x Precision + Recall. beta 만큼 재현율에 가중치를 줌

##### ROC(Receiver Operating Characteristic) 그래프
* x축에는 FP Ratio( 1 - 특이도)를 나타내며, y축에는 민감도를 나타냄
* AUC이 넓을수록 좋은 모형으로 평가

##### 이익도표와 향상도 곡선
* 이익(gain)은 목표 범주에 속하는 개체들이 각 등급에 얼마나 분포하고 있는지를 나타내는 값
* 분류된 관측치가 각 등급별로 얼마나 포함되는지를 나타내는 도표
* 향상도 곡선은 랜덤모델과 비교하여 해당 모델의 성과가 얼마나 향상되었는지를 각 등급별로 파악
* 상위 등급에서 향상도가 크고, 하위 등급에서 향상도가 작으면 좋은 모델로 생각할 수 있음
* ex) 각 데이터에서의 예측 확률(prob)을 계산할 수 있고, 이 값을 내림차순으로 정렬할 수 있음  
상위에서 하위로 갈수록 정확도가 떨어진다면 좋은 모델이라는 의미

### 군집 분석
* 군집분석은 이상값탐지에도 사용
* 군집화방법에는 계층적군집, 분리(partitioning)군집, 밀도-기반군집, 모형-기반군집, 격자-기반군집, 커널-기반군집, SOM 방법 등이 존재

#### 계층적 군집
* 가장 유사한 개체를 묶어 나가는 과정을 반복하여 원하는 개수의 군집을 형성하는 방법
* 계통도 또는 덴드로그램(dendrogram) 형태로 결과가 주어짐
* 각 개체는 하나의 군집에만 포함 됨
* 군집간의 연결법에 따라 군집의 결과가 달라짐
* 계층적군집 형성 방법은 작은 군집에서 출발하여 군집을 병합해 나가는 병합적 방법과 큰 군집에서 출발하여 분리해 나가는 분할적 방법이 존재
* 거리 측정 방법
  * 최단연결법 또는 단일연결법(single linkage method) : 각 군집 내의 각 거리를 계산해 최단 거리 선택
  * 최장연결법 또는 완전연결법(complete linkage method) : 최장 거리 선택
  * 중심연결법(centroid linkage) : 두 군집 중심 간의 거리 측정
  * 평균연결법(average linkage) : 모든 항목에 대한 거리 평균 계산
  * 와드연결법(ward linkage) : 군집내의 오차 제곱합에 기초하여 군집 수행. 군집이 합해졌을 때 오차제곱합이 가장 적게 커지는 군집을 합침
* 변수가 연속형인 경우, 다양한 거리 사용
  * 유클리드 거리
  * 맨하튼, 시가 거리
  * 민코우스키 거리
  * 표준화 거리 : 변수의 측정 단위를 표준화한 거리
  * 마할라노비스 거리 : 변수의 표준화와 함께 변수 간의 상관성을 동시에 고려한 통계적 거리
* 명목형인 경우 다음과 같이 거리가 계산될 수 있음
  * d(i, j) : 개체 i와 j에서 다른 값을 가지는 변수의 수 / 총변수의 수
  * 단순 일치 계수(유사성 측도)
  * 자카드 계수 이용
*  순서형인 경우
   * 순위 상관 계수
*  군집을 형성하는 매 단계에서 지역적 최적화를 수행해 나가는 방법을 사용하므로, global한 최적해라고 보기 어려움
* 한번 군집이 형성되면 다른 군집으로 이동할 수 없음  

#### k-평균 군집
* 원하는 군집 수 만큼 초기값 지정, 각 개체를 가까운 초기값에 할당하여 군집을 형성한 뒤, 각 군집의 평균을 재계산하여 초기값 갱신
* 갱신된 값에 대해 위의 할당과정 반복
* k-means 알고리즘 절차
  * 초기 중심으로 k개의 객체를 임의 선택
  * 각 자료를 가장 가까운 군집 중심 할당(오차제곱합이 최소가 되도록 각 자료 할당)
  * 각 군집 내의 자료들의 평균을 계산하여 군집의 중심 갱신
  * 군집 중심의 변화가 없을 때까지 단계2와 단계3 반복
* 초기의 k 위치에 따라 군집 결과가 크게 달라질 수 있음
* k-means 군집방법은 군집의 매 단계마다 군집 중심으로부터 오차제곱합을 최소화하는 방향으로 군집을 형성해가는 greedy algorithm 으로 간주
* 알고리즘이 단순
* 빠르게 수행되며, 계층적 군집보다 많은 양의 자료를 다룰 수 있음
* 평균 등 거리 계산에 기반하므로 모든 변수가 연속형이어야 함
* 잡음, 이상값에 영향을 많이 받음
* U - 형태의 군집이 존재할 경우, 성능이 많이 떨어짐
* 평균값이 아닌 중앙값을 사용하는 k-medoids 군집을 사용할 수 있음 ( pam 함수 이용)

#### 혼합 분포 군집(mixture distribution clustering)
* 모형-기반(model-based) 의 군집 방법
* 데이터가 k개의 모수적 모형의 가중합으로 표현되는 모집단 모형으로부터 나왔다는 가정하에서 모수와 함께 가중치를 자료로부터 추정하는 방법 사용
* k개의 각 모형은 군집을 의미
* 각 데이터는 추정된 k개의 모형 중 어느 모형으로부터 나왔을 확률이 높은지에 따라 군집의 분류가 이루어짐
* 혼합모형에서의 모수와 가중치 추정에는 EM 알고리즘 사용
* 최대가능도추정을 위한 수치적 방법
* 초기값의 설정이 필요 없음
* 해킹을 당하는 컴퓨터를 발견할 때 사용
* EM 알고리즘
  * 편의상 모집단을 구성하는 각 집단의 분포는 정규분포를 따른다고 가정
  * 각 자료가 M개 중 어느 집단으로부터 나온 것인지를 안다면 모수 추정이 어렵지 않음
  * 각 자료가 어느 집단에 속하는지에 대한 정보를 가지는 잠재변수(latent variable)를 도입
* 모수 추정에서 데이터가 커지면 수렴하는데 시간이 걸릴 수 있으며, 군집의 크기가 너무 작으면 추정의 정도가 떨어지거나 어려울 수 있음

#### SOM(Self-Organizing Maps)
* 비지도 신경망으로 고차원의 데이터를 이해하기 쉬운 저차원의 뉴런으로 정렬하여 지도 형태로 형상화
* 입력 변수의 위치 관계를 그대로 보존한다는 특징이 있음  
다시 말해 실제 공간의 입력 변수가 가까이 있으면, 지도상에서도 가까운 위치에 있게 됨
* 이러한 특징으로 인해 입력 변수의 정보와 그들의 관계가 지도상에 그대로 나타남
* 두 개의 인공신경망 층으로 구성
  * 입력층(입력 변수의 개수와 동일)
  * 경쟁층(입력벡터의 특성에 따라 벡터가 한 점으로 클러스터링 되는 층, 클러스터링 개수만큼 뉴런 수가 존재)
* 입력층의 자료는 학습을 통해서 경쟁층에 정렬되는데 이를 map 이라고 부름
* 입력층과 경쟁층은 완전 연결(fully connected) 되어 있음
* 각 학습 단계마다 입력층의 데이터 집합으로부터 하나의 표본 벡터 x 가 임의로 선택되었을 때 프로토타입 벡터(경쟁층의 각 뉴런을 의미)와의 거리를 유클리드 거리로 계산하고 비교
* 입력 층의 표본 벡터에 가장 가까운 프로토타입 벡터를 선택항 BMU라 명명
* 위상학적 이웃(topological neighbors)에 대한 연결 강도를 조정
* SOM은 경쟁 학습으로 각각의 뉴런이 입력 벡터와 얼마나 가까운가를 계산하여 연결 강도를 반복적으로 재조정하여 학습
* 이러한 과정을 거치면서 연결강도는 입력 패턴과 가장 유사한 경쟁층 뉴런이 승자가 됨
* SOM을 이용한 군집 분석은 feed-forward flow 를 사용
* 속도가 빨라 실시간 학습 처리가 가능

### 연관 분석(association Rule)  
#### 연관 규칙
* 항목들간의 조건-결과 식으로 표현되는 유용한 패턴
* 흔히 장바구니분석(market basket)라고도 함
* 특정 고객, 장바구니 하나에 해당하는 정보를 트랜잭션(transantion) 이라 함

#### 연관규칙의 측정지표
* 도출된 모든 규칙이 유의미한 것인지 확인해야 함. 따라서 도출된 연관 규칙이 얼마나 유의미한지 평가하기 위한 몇 가지 측정지표는 다음과 같음
* 지지도(support)
  * 전체 거래 중에서 품목 A, B가 동시에 포함되는 거래의 비율
  * 전체 구매 경향을 파악할 수 있음
  * 지지도 = P(A n B) = A와 B가 동시에 포함된 거래수 / 전체거래수
*  신뢰도(confidence)  
   * 품목 A가 포함된 거래 중에서 품목 A, B를 동시에 포함하는 거래 확률
   * 신뢰도 = P(A n B ) / P(A)
* 향상도(lift)
   * 품목 B를 구매한 고객 대비 품목 A를 구매한 후 품목 B를 구매하는 고객에 대한 확률
   * 향상도 = P(B|A) / P(B) = P(A n B) / P(A) * P(B) = A와 B를 포함하는 거래수 / A 거래수 * B 거래수
   * 품목 A와 품목 B의 구매가 서로 독립적인 경우, P(B|A) = P(B) 가 되므로, 향상도는 1이 됨
   * 향상도가 1보다 크면, 이 규칙은 결과를 예측하는 데 있어 우수하다는 것을 의미
   * 1보다 작으면 우연적 기회보다 도움이 되지 않음을 의미
   * 1보다 크면 품목 A를 구매한 후에 B를 구매할 확률이 단순 B를 구매할 확률보다 높음을 의미   
* 모든 경우의 수를 계산하는 것은 어려운 일이므로, 최소 지지도를 정해 규칙 도출  
10% -> 5% -> 1% -> 0.1%와 같이 낮추어가며 실행해야 효율적

#### 연관 분석 절차
* 최소 지지도를 갖는 연관규칙을 찾는 대표적인 방법인 Apriori 알고리즘이 있음
* 최소 지지도보다 큰 집합만을 대상으로 높은 지지도를 갖는 품목 집합을 찾는 것
* Apriori 알고리즘이 분석 절차
  * 최소 지지도 설정
  * 개별 품목 중에서 최소 지지도를 넘는 모든 품목을 찾음
  * 2에서 찾은 개별 품목만을 이용하여 최소 지지도를 넘는 2가지 품목 집합을 찾음
  * 위의 두 절차에서 찾은 품목 집합을 결합하여 최소 지지도를 넘는 3가지 품목 집합을 찾음
  * 반복적으로 수행해 최소 지지도가 넘는 빈발품목 집합을 찾음

#### 연관 분석 장점
* 탐색적인 기법 : 연관 분석 결과를 이해하기 쉬움
* 강력한 비목적성 분석기법 : 목적변수가 없을 때 유리
* 사용이 편리한 분석 데이터의 형태 : 거래 내용에 대한 데이터를 변환 없이 그 자체로 이용할 수 있는 간단한 자료구조를 갖는 분석방법
* 계산의 용이성 : 분석을 위한 계산이 상당히 간단

#### 연관규칙의 단점
* 품목수 증가시 복잡
* 적절한 품목의 결정이 어렵. 너무 세분화된 품목을 가지고 연관규칙을 찾으려고 하면 의미 없는 분석 결과 나옴
* 품목의 비율차이 : 상대적으로 거래 수가 적은 품목은 규칙 발견시 제외되기 쉬움

#### 순차패턴
* 구매시점에 대한 데이터를 통해 효과적으로 연관 분석을 수행 할 수 있음



#### 용어 정리
* 공변량(covariate) : 공변량이라는 변수는 독립변수라기 보다는 하나의 개념으로서 여러 변수들이 공통적으로 함께 공유하고 있는 변량을 뜻한다.
* 정지규칙 : 더 이상 분리가 일어나지 않고 현재의 마디가 끝마디가 되도록 하는 여러 가지 규칙으로 최대 나무의 깊이, 자식마디의 최소 관측치 수, 카이제곱 통계량, 지니 지수, 엔트로피 지수 등이 있음
* 가지치기는 분류된 관측치의 비율, MSE 등을 고려하여 수준의 가지치기 규칙을 제공
* out-of-bag : bootstrap 과정에서 제외된 데이터를 말함
=======
## 정형 데이터 마이닝
### 데이터 마이닝 개요
* 데이터 마이닝의 6가지 기능
  * 분류(Classification)
  * 추정(Estimation)  : 연속된 변수의 값을 추정하는데 사용
  ex) 가족 구성원의 총 수입, 고객의 평생 가치 등..
  * 예측(Prediction) : 장바구니 분석
  * 연관 분석(Association Analysis)
  * 군집(Clustering)
  * 기술(Description)
* 데이터 마이닝 기능을 추진하기 위한 5단계
  * 목적 정의
  * 데이터 준비
  * 데이터 가공
  * 데이터 마이닝 기법의 적용
    * 목적 정의 단계에서 데이터 마이닝 기법을 결정하는 것이 좋음
  * 검증

### 분류 분석
* 많이 사용되는 분류 모형
  * 로지스틱회귀, 신경망, 의사결정나무, 앙상블, 규칙기반, 사례기반, 인접이웃, 베이즈, SVM, 유전자 알고리즘 등

#### 로지스틱 회귀모형
* 모형의 적합을 통해 추정된 확률를 사후 확률이라 부르기도 함
* 오즈(odds)의 관점에서 해석될 수 있다는 장점을 가짐
* exp(B1) 의 의미는 x1이 한단계 증가할 때 마다 성공(Y=1)의 오즈가 몇 배 증가하는지를 나타내는 값
* 로지스틱회귀가 분류의 목적으로 사용될 경우에는 Pi(x) 가 기준값 보다 크면 Y = 1 인 집단으로, 작으면
*  Y = 0인 집단으로 분류하게 됨
* 분류기준값의 결정은 정분류율, 민감도, 특이도를 동시에 고려하는 등의 다양한 방법이 사용됨
*

#### 신경망 모형
* 입력층이 직접 출력층에 연결되는 단층신경망(퍼셉트론이라고 불리기도 함)
* z = w'x + w0
* z값에 대해 활성함수가 적용되어 y(x)가 계산됨
* 이 시스템에서 가중치 w는 의사결정 경계(decision boundary)의 방향을 나타내는 모수
* Wo는 의사결정 경계의 위치를 결정하는 모수
* 가중치 W와 Wo는 오차제곱합이 최소가 되는 방향으로 갱신됨
* 최종 목표값 y는 z에 대해 비선형 활성함수 파이(')를 적용하여 구해짐
* 많이 사용되는 활성화 함수
  * 부호(sign) 또는 threshold 함수 : 결과는 -1 또는 1
  * 계단(step) 함수 : 결과는 이진형 0, 1
  * 시그모이드 함수 : 결과는 연속형이며, 0 <= y < = 1
  * SoftMax 함수 : 표준화지수(일반화로지스틱) 함수로도 불리며, 출력값 z가 여러 개로 주어지고, 목표치가 다범주인 경우 각 범주에 속할 사후 확률을 제공
  * tanh 함수 : 결과는 연속형이며, -1 <= y <= 1
  * 가우스 함수 : 결과는 연속형이며, 0 <= y <= 1

#### 다층 신경망
* 여러개의 은닉층(hidden layer)를 가지는 신경망 구조
* 다층신경망의 가중치는 학습과정에서 오차의 역전파 알고리즘을 통해 갱신됨
* 은닉층의 수는 의사결정 경계를 정하는데 중요
* 은닉층의 수를 정할 때는 다음의 사항을 고려함
  * 다층신경망은 훈련이 어렵
  * 시그모이드 활성함수를 가지는 2개 층의 네트워크는 임의의 의사결정 경계를 모형화 할 수 있음
* 각 층의 노드 수의 결정은 다음을 고려하여 결정
  * 출력층 노드의 수는 출력 범주의 수로 결정
  * 입력의 수는 입력 차원의 수로 결정
  *  은닉층 노드의 수는 너무 적으면 복잡한 의사결정 경계를 만들 수 없고, 너무 많으면 네트워크 일반화가 어려움

* 신경망 모형의 장점
  * 변수의 수가 많거나 입, 출력 변수 간의 복잡한 비선형 관계가 존재하는 경우 유용
  * 잡음에 대해서도 민감하게 반응 X
* 신경망 모형의 단점
  * 결과 해석이 어려움
  * 모형이 복잡하면 훈련과정에 시간이 많이 소요   

#### 의사결정나무 모형  
* 상위노드에서의 분류변수, 분류기준값은 이 기준에 의해 분기되는 하위노드에서 노드 내에서는 동질성이 노드 사이에서는 이질성이 가장 커지도록 선택
* 나무 모형의 크기는 과대적합 되지 않도록 합리적 기준에 의해 적당히 조절되어야 함
* 더 이상 분기되지 않는 노드를 최종 마디(terminal node) 라고 함
* 가지분할(split)은 나무의 가지를 생성하는 과정을, 가지치기(pruning)은 생성된 가지를 잘라내어 모형을 단순화하는 과정을 말함
* 목표변수가 이산형인 경우 분류기준값 종류
  * 카이제곱 통계량의 p-값
  * 지니 지수
  * 엔트로피 지수  
* p-값은 그 값이 작을 수록 자식노드 내의 이질성이 큼을 의미
* 지니 지수나 엔트로피 지수는 그 값이 클수록 자식노드 내의 이질성이 큼을 의미
* 목표변수가 연속형인 경우 분류기준값 종류
  * F-통계량의 p-값
  * 분산의 감소량
* p-값이 작아지는 방향으로 가지분할 수행.  
분산의 감소량(variance reduction)은 커지는 방향으로 가지분할 수행
* 의사결정나무의 분석과정
  * 목표변수와 관계가 있는 설명변수들의 선택
  * 분석목적과 자료의 구조에 따라 적절한 분리기준과 정지규칙을 정하여 의사결정나무 생성
  * 부적절한 나뭇가지는 제거
  * 이익, 위험, 비용 등을 고려하여 모형 평가
  * 분류 및 예측
* 의사결정나무분석을 위한 알고리즘 : CHAID, CART, ID3, C4.5, C5.0 등
* 주요 알고리즘 vs 분류 기준변수의 선택법
  * CHAID : 카이제곱 통계량, ANOVA F-통계량
  * CART : 지니지수, 분산감소량
  * C4.5 : 엔트로피지수

* 의사결정나무의 장점
  * 구조가 단순하여 해석이 용이
  * 유용한 입력변수의 파악과 예측변수간의 상호작용 및 비선형성을 고려하여 분석이 수행
  * 선형성, 정규성, 등분산성 등의 수학적 가정이 불필요한 비모수적 모형
* 의사결정나무의 단점
  * 분류기준값의 경계선 근방의 자료값에 대해서는 오차가 큼
  * 로지스틱회귀와 같이 각 예측변수의 효과를 파악하기 어려움
  * 새로운 자료에 대한 예측이 불안정할 수 있음

#### 앙상블 모형
* 여러 개의 분류모형에 대한 결과를 종합하여 분류의 정확도를 높이는 방법
* 적절한 표본추출법으로 데이터에서 여러 개의 훈련용 데이터 집합을 만들어 각 데이터 집합에서 하나의 분류기를 만들어 앙상블하는 방법
* 데이터 조절 방법 : bagging, boosting
* randomForest 모형은 배깅의 기념과 feature의 임의선택을 결합한 앙상블 기법   

##### 베깅
* 배깅은 bootstrap aggregating의 준말로, 원 데이터 집합에서 크기가 같은 표본을 여러번 단순 임의 복원추출하여 각 표본에 대해 분류기를 생성한 후 그 결과를 앙상블하는 방법

##### 부스팅
* 배깅의 과정과 유사하나 붓스트랩 표본을 구성하는 재표본(re-sampling) 과정에서 각 자료에 동일한 확률을 부여하는 것이 아니라,  분류가 잘못된 데이터에 더 큰 가중을 두어 표본 추출
* 아다부스팅(AdaBoosting : adaptive boosting)은 가장 많이 사용되는 부스팅 알고리즘

##### 랜덤포레스트
* 배깅에 랜덤 과정을 추가한 방법
*  부트스트랩 방식에서 예측변수를 임의로 추출하고, 추출된 변수 내에서 최적의 분할을 만들어 나가는 방식
* 새로운 자료에 대한 예측은 분류는 다수결로, 회귀의 경우에는 평균을 취하는 방법으로 사용

#### 모형평가
* 모형평가의 기준은 크게 일반화의 가능성, 효율성, 예측과 분류의 정확성으로 구분
  * 일반화의 가능성 : 같은 모집단 내에 다른 데이터에 적용하는 경우에도 안정적인 결과를 제공하는 것을 의미
  * 효율성 : 분류 분석 모형이 얼마나 효과적으로 구축되었는지 평가  
  적은 입력변수를 필요로 할수록 효율성이 높다고 할 수 있음
  * 예측과 분류의 정확성 : 구축된 모형의 정확성 측면에서 평가하는 것
  * test data를 추출함으로써 2종 오류의 발생을 방지. 이 단계를 위하여 사용되는 추출 방법은 hold-out, cross-validation, bootstrap 방법 등이 존재
    * hold-out : raw data에서 Training/Test data로 구분하는 것
    * cross-validation
    * bootstrap : cv와 유사하나 복원 추출한다는 점에서 차이가 있음. 데이터의 수가 적을 때 많이 활용
* 분류 모형 평가에는 오분류표, ROC 그래프, 이익 도표, 향상도 곡선 등이 존재

##### 오분류표(confusion matrix)
* TP(True Positive) : 실제값과 예측치 모두 True인 경우
* TN(True Negative) : 실제값과 예측치 모두 Fasle인 빈도
* FP(False Positive) : 실제값은 False 이나 True로 예측한 빈도
* FN(False Negative) : 실제값은 True 이나 False로 예측한 빈도

* 정분류율 : TP + TN / P + N, 범주의 분포가 균형을 이룰 때 효과적임
* 오분류율 : FP + FN / P + N,
* 민감도(Sensitivity) : TP / P : 실제값이 True인 관측치중  예측치가 적중한 정도
* 특이도(specificity) : TN / N : 실제값이 False인 관측치중 예측치가 적중한 정도
* 정확도(precision) : TP / TP  + FP = True로 예측한 관측치 중 실제로 True인 비율
* 재현율(recall) : 실제값이 True인 관측치 중 예측치가 적중한 정도. (민감도와 동일 지표)
* F1 = 2 x 정확도 x 재현율 / 정확도 + 재현율
* F(beta) =  (1 + beta^2 ) x Precision x Recall / beta ^  2 x Precision + Recall. beta 만큼 재현율에 가중치를 줌

##### ROC(Receiver Operating Characteristic) 그래프
* x축에는 FP Ratio( 1 - 특이도)를 나타내며, y축에는 민감도를 나타냄
* AUC이 넓을수록 좋은 모형으로 평가

##### 이익도표와 향상도 곡선
* 이익(gain)은 목표 범주에 속하는 개체들이 각 등급에 얼마나 분포하고 있는지를 나타내는 값
* 분류된 관측치가 각 등급별로 얼마나 포함되는지를 나타내는 도표
* 향상도 곡선은 랜덤모델과 비교하여 해당 모델의 성과가 얼마나 향상되었는지를 각 등급별로 파악
* 상위 등급에서 향상도가 크고, 하위 등급에서 향상도가 작으면 좋은 모델로 생각할 수 있음
* ex) 각 데이터에서의 예측 확률(prob)을 계산할 수 있고, 이 값을 내림차순으로 정렬할 수 있음  
상위에서 하위로 갈수록 정확도가 떨어진다면 좋은 모델이라는 의미

### 군집 분석
* 군집분석은 이상값탐지에도 사용
* 군집화방법에는 계층적군집, 분리(partitioning)군집, 밀도-기반군집, 모형-기반군집, 격자-기반군집, 커널-기반군집, SOM 방법 등이 존재

#### 계층적 군집
* 가장 유사한 개체를 묶어 나가는 과정을 반복하여 원하는 개수의 군집을 형성하는 방법
* 계통도 또는 덴드로그램(dendrogram) 형태로 결과가 주어짐
* 각 개체는 하나의 군집에만 포함 됨
* 군집간의 연결법에 따라 군집의 결과가 달라짐
* 계층적군집 형성 방법은 작은 군집에서 출발하여 군집을 병합해 나가는 병합적 방법과 큰 군집에서 출발하여 분리해 나가는 분할적 방법이 존재
* 거리 측정 방법
  * 최단연결법 또는 단일연결법(single linkage method) : 각 군집 내의 각 거리를 계산해 최단 거리 선택
  * 최장연결법 또는 완전연결법(complete linkage method) : 최장 거리 선택
  * 중심연결법(centroid linkage) : 두 군집 중심 간의 거리 측정
  * 평균연결법(average linkage) : 모든 항목에 대한 거리 평균 계산
  * 와드연결법(ward linkage) : 군집내의 오차 제곱합에 기초하여 군집 수행. 군집이 합해졌을 때 오차제곱합이 가장 적게 커지는 군집을 합침
* 변수가 연속형인 경우, 다양한 거리 사용
  * 유클리드 거리
  * 맨하튼, 시가 거리
  * 민코우스키 거리
  * 표준화 거리 : 변수의 측정 단위를 표준화한 거리
  * 마할라노비스 거리 : 변수의 표준화와 함께 변수 간의 상관성을 동시에 고려한 통계적 거리
* 명목형인 경우 다음과 같이 거리가 계산될 수 있음
  * d(i, j) : 개체 i와 j에서 다른 값을 가지는 변수의 수 / 총변수의 수
  * 단순 일치 계수(유사성 측도)
  * 자카드 계수 이용
*  순서형인 경우
   * 순위 상관 계수
*  군집을 형성하는 매 단계에서 지역적 최적화를 수행해 나가는 방법을 사용하므로, global한 최적해라고 보기 어려움
* 한번 군집이 형성되면 다른 군집으로 이동할 수 없음  

#### k-평균 군집
* 원하는 군집 수 만큼 초기값 지정, 각 개체를 가까운 초기값에 할당하여 군집을 형성한 뒤, 각 군집의 평균을 재계산하여 초기값 갱신
* 갱신된 값에 대해 위의 할당과정 반복
* k-means 알고리즘 절차
  * 초기 중심으로 k개의 객체를 임의 선택
  * 각 자료를 가장 가까운 군집 중심 할당(오차제곱합이 최소가 되도록 각 자료 할당)
  * 각 군집 내의 자료들의 평균을 계산하여 군집의 중심 갱신
  * 군집 중심의 변화가 없을 때까지 단계2와 단계3 반복
* 초기의 k 위치에 따라 군집 결과가 크게 달라질 수 있음
* k-means 군집방법은 군집의 매 단계마다 군집 중심으로부터 오차제곱합을 최소화하는 방향으로 군집을 형성해가는 greedy algorithm 으로 간주
* 알고리즘이 단순
* 빠르게 수행되며, 계층적 군집보다 많은 양의 자료를 다룰 수 있음
* 평균 등 거리 계산에 기반하므로 모든 변수가 연속형이어야 함
* 잡음, 이상값에 영향을 많이 받음
* U - 형태의 군집이 존재할 경우, 성능이 많이 떨어짐
* 평균값이 아닌 중앙값을 사용하는 k-medoids 군집을 사용할 수 있음 ( pam 함수 이용)

#### 혼합 분포 군집(mixture distribution clustering)
* 모형-기반(model-based) 의 군집 방법
* 데이터가 k개의 모수적 모형의 가중합으로 표현되는 모집단 모형으로부터 나왔다는 가정하에서 모수와 함께 가중치를 자료로부터 추정하는 방법 사용
* k개의 각 모형은 군집을 의미
* 각 데이터는 추정된 k개의 모형 중 어느 모형으로부터 나왔을 확률이 높은지에 따라 군집의 분류가 이루어짐
* 혼합모형에서의 모수와 가중치 추정에는 EM 알고리즘 사용
* 최대가능도추정을 위한 수치적 방법
* 초기값의 설정이 필요 없음
* 해킹을 당하는 컴퓨터를 발견할 때 사용
* EM 알고리즘
  * 편의상 모집단을 구성하는 각 집단의 분포는 정규분포를 따른다고 가정
  * 각 자료가 M개 중 어느 집단으로부터 나온 것인지를 안다면 모수 추정이 어렵지 않음
  * 각 자료가 어느 집단에 속하는지에 대한 정보를 가지는 잠재변수(latent variable)를 도입
* 모수 추정에서 데이터가 커지면 수렴하는데 시간이 걸릴 수 있으며, 군집의 크기가 너무 작으면 추정의 정도가 떨어지거나 어려울 수 있음

#### SOM(Self-Organizing Maps)
* 비지도 신경망으로 고차원의 데이터를 이해하기 쉬운 저차원의 뉴런으로 정렬하여 지도 형태로 형상화
* 입력 변수의 위치 관계를 그대로 보존한다는 특징이 있음  
다시 말해 실제 공간의 입력 변수가 가까이 있으면, 지도상에서도 가까운 위치에 있게 됨
* 이러한 특징으로 인해 입력 변수의 정보와 그들의 관계가 지도상에 그대로 나타남
* 두 개의 인공신경망 층으로 구성
  * 입력층(입력 변수의 개수와 동일)
  * 경쟁층(입력벡터의 특성에 따라 벡터가 한 점으로 클러스터링 되는 층, 클러스터링 개수만큼 뉴런 수가 존재)
* 입력층의 자료는 학습을 통해서 경쟁층에 정렬되는데 이를 map 이라고 부름
* 입력층과 경쟁층은 완전 연결(fully connected) 되어 있음
* 각 학습 단계마다 입력층의 데이터 집합으로부터 하나의 표본 벡터 x 가 임의로 선택되었을 때 프로토타입 벡터(경쟁층의 각 뉴런을 의미)와의 거리를 유클리드 거리로 계산하고 비교
* 입력 층의 표본 벡터에 가장 가까운 프로토타입 벡터를 선택항 BMU라 명명
* 위상학적 이웃(topological neighbors)에 대한 연결 강도를 조정
* SOM은 경쟁 학습으로 각각의 뉴런이 입력 벡터와 얼마나 가까운가를 계산하여 연결 강도를 반복적으로 재조정하여 학습
* 이러한 과정을 거치면서 연결강도는 입력 패턴과 가장 유사한 경쟁층 뉴런이 승자가 됨
* SOM을 이용한 군집 분석은 feed-forward flow 를 사용
* 속도가 빨라 실시간 학습 처리가 가능

### 연관 분석(association Rule)  
#### 연관 규칙
* 항목들간의 조건-결과 식으로 표현되는 유용한 패턴
* 흔히 장바구니분석(market basket)라고도 함
* 특정 고객, 장바구니 하나에 해당하는 정보를 트랜잭션(transantion) 이라 함

#### 연관규칙의 측정지표
* 도출된 모든 규칙이 유의미한 것인지 확인해야 함. 따라서 도출된 연관 규칙이 얼마나 유의미한지 평가하기 위한 몇 가지 측정지표는 다음과 같음
* 지지도(support)
  * 전체 거래 중에서 품목 A, B가 동시에 포함되는 거래의 비율
  * 전체 구매 경향을 파악할 수 있음
  * 지지도 = P(A n B) = A와 B가 동시에 포함된 거래수 / 전체거래수
*  신뢰도(confidence)  
   * 품목 A가 포함된 거래 중에서 품목 A, B를 동시에 포함하는 거래 확률
   * 신뢰도 = P(A n B ) / P(A)
* 향상도(lift)
   * 품목 B를 구매한 고객 대비 품목 A를 구매한 후 품목 B를 구매하는 고객에 대한 확률
   * 향상도 = P(B|A) / P(B) = P(A n B) / P(A) * P(B) = A와 B를 포함하는 거래수 / A 거래수 * B 거래수
   * 품목 A와 품목 B의 구매가 서로 독립적인 경우, P(B|A) = P(B) 가 되므로, 향상도는 1이 됨
   * 향상도가 1보다 크면, 이 규칙은 결과를 예측하는 데 있어 우수하다는 것을 의미
   * 1보다 작으면 우연적 기회보다 도움이 되지 않음을 의미
   * 1보다 크면 품목 A를 구매한 후에 B를 구매할 확률이 단순 B를 구매할 확률보다 높음을 의미   
* 모든 경우의 수를 계산하는 것은 어려운 일이므로, 최소 지지도를 정해 규칙 도출  
10% -> 5% -> 1% -> 0.1%와 같이 낮추어가며 실행해야 효율적

#### 연관 분석 절차
* 최소 지지도를 갖는 연관규칙을 찾는 대표적인 방법인 Apriori 알고리즘이 있음
* 최소 지지도보다 큰 집합만을 대상으로 높은 지지도를 갖는 품목 집합을 찾는 것
* Apriori 알고리즘이 분석 절차
  * 최소 지지도 설정
  * 개별 품목 중에서 최소 지지도를 넘는 모든 품목을 찾음
  * 2에서 찾은 개별 품목만을 이용하여 최소 지지도를 넘는 2가지 품목 집합을 찾음
  * 위의 두 절차에서 찾은 품목 집합을 결합하여 최소 지지도를 넘는 3가지 품목 집합을 찾음
  * 반복적으로 수행해 최소 지지도가 넘는 빈발품목 집합을 찾음

#### 연관 분석 장점
* 탐색적인 기법 : 연관 분석 결과를 이해하기 쉬움
* 강력한 비목적성 분석기법 : 목적변수가 없을 때 유리
* 사용이 편리한 분석 데이터의 형태 : 거래 내용에 대한 데이터를 변환 없이 그 자체로 이용할 수 있는 간단한 자료구조를 갖는 분석방법
* 계산의 용이성 : 분석을 위한 계산이 상당히 간단

#### 연관규칙의 단점
* 품목수 증가시 복잡
* 적절한 품목의 결정이 어렵. 너무 세분화된 품목을 가지고 연관규칙을 찾으려고 하면 의미 없는 분석 결과 나옴
* 품목의 비율차이 : 상대적으로 거래 수가 적은 품목은 규칙 발견시 제외되기 쉬움

#### 순차패턴
* 구매시점에 대한 데이터를 통해 효과적으로 연관 분석을 수행 할 수 있음



#### 용어 정리
* 공변량(covariate) : 공변량이라는 변수는 독립변수라기 보다는 하나의 개념으로서 여러 변수들이 공통적으로 함께 공유하고 있는 변량을 뜻한다.
* 정지규칙 : 더 이상 분리가 일어나지 않고 현재의 마디가 끝마디가 되도록 하는 여러 가지 규칙으로 최대 나무의 깊이, 자식마디의 최소 관측치 수, 카이제곱 통계량, 지니 지수, 엔트로피 지수 등이 있음
* 가지치기는 분류된 관측치의 비율, MSE 등을 고려하여 수준의 가지치기 규칙을 제공
* out-of-bag : bootstrap 과정에서 제외된 데이터를 말함
>>>>>>> d568c93468e8da4bd62a01269ea2d4e8a8e727a1
