# :fire:1장 한눈에 보는 머신러닝
* 1.1 머신러닝이란?
* 1.2 왜 머신러닝을 사용하는가?
* 1.3 머신러닝 시스템의 종류
* 1.4 머신러닝의 주요 도전 과제
* 1.5 테스트와 검증
* 1.6 연습문제
## 1.1 머신러닝이란?
  * 데이터로부터 학습하도록 컴퓨터를 프로그래밍하는 과학.
  * 명시적인 프로그래밍 없이 컴퓨터가 학습하는 능력을 갖추게 하는 연구 분야.
  
   **기초 개념>**
	 예시) 스팸 필터 : 스팸 메일과 일반 메일의 샘플을 이용해 스팸 메일 구분법을 배울 수 있는 머신러닝
* 훈련 세트 : 스팸메일과 일반 메일의 샘플 / 시스템이 학습하는데 사용하는 샘플
* 훈련 사례(샘플) : 작업T는 새로운 메일이 스팸인지 구분 / 각 훈련의 데이터
* 훈련 데이터 : 경험E
* 정확도 : 성능 측정 P는 정확히 분류된 메일의 비율
	      
##  1.2 왜 머신러닝을 사용하는가?
* 전통적인 프로그래밍 기법을 사용하면 문제가 단순하지 않아 규칙이 점점 길고 복잡해지므로 유지보수가 매우 힘들다.
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/01.png"/>
* 머신러닝 기법을 사용하면 프로그램이 훨씬 짧아지고 유지 보수하기 쉬우며 대부분 정확도가 높다.
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/02.png"/>

## 1.3 머신러닝 시스템의 종류
### 사람의 감독 하에 훈련 유/무
- 지도 학습 : 알고리즘에 주입하는 훈련 데이터에 레이블이라는 원하는 답이 포함
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/05.png"/>  
	* A라는 메일의 훈련데이터에 이것은 스팸이다!

- 비지도 학습 : 말 그대로 훈련 데이터에 레이블(답)이 없이 시스템이 알아서 학습
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/06.png"/>
	* 컴퓨터가 스스로 훈련세트를 통해서 통계적인 계산을 해서 어떤 조건이면 이것은 스팸이다, 아니다를 판단하는 것을 말한다.

- 비지도 학습 알고리즘 : 군집, 시각화와 차원 축소, 연관 규칙 학습

	* 계층 군집 : 비슷한 것끼지 그룹으로 묶음 // Ex. 블로그 방문자에 대한 데이터
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/07.png"/>
	* 차원 축소 : 너무 많은 정보를 잃지 않으면서 데이터를 간소화 상관관계가 있는 여러 특성을 하나로 합치는 것이다.

	* 이상치 탐지 : 학습 알고리즘에 주입하기 전에 데이터셋에서 이상한 값을 자동으로 제거
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/08.png"/>
	* 연관 규칙 학습 : 대량의 데이터에서 특성 간의 흥미로운 관계를 찾음

		* 바비큐 소스와 감자를 산 사람이 스테이크도 구매하는 경향이 있다.

- 준지도 학습 : 지도 학습과 비지도 학습의 중간정도 단계, 일부는 레이블(답)이 있고 일부는 레이블이 없는 세트를 훈련시켜서 답을 찾는 과정이다.
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/09.png"/>
	* 구글 포토 호스팅 서비스_사진마다 답이 하나씩 주어지면 사진에 있는 모든 사람의 이름을 알 수 있다.

- 강화 학습 : 매우 다른 종류의 알고리즘, 학습하는 시스템을 에이전트라고 부르며 환경을 관찰해서 행동을 실행하고 그 결과로 보상 or 벌점 주게되어 시간이 지나면서 가장 큰 보상을 받은 정책(최상의 전략)을 스스로 학습
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/10.png"/>
	* 알파고

### 실시간으로 점진적인 학습 유/무

- 배치 학습 : 기존의 학습을 할 때 약 10000개 정도 되는 데이터샘플들을 사용한다 했을 때, 한 번에 이 많은 데이터를 모두 훈련시키고 실행하는 방식, 간단하고 잘 작동하지만 훈련시킬 때는 상당히 오랜시간이 걸린다

- 온라인 학습 : 데이터를 조금씩 나눠서 학습하는 방식. 작은 묶음단위로 학습하기 때문에 매 학습할 때 시간이 적게 소요된다. 주로 주식가격이라든가 빠른 변화가 필요한 사례에 적합하다.
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/11.png"/>

### 단순하게 알고 있는 데이터 포인트와 새 데이터 포인트를 비교하는 것인지, 아니면 훈련 데이터셋에서 과학자들처럼 패턴을 발견하여 예측 모델을 만드는지
* 사례 기반 학습 : 단순히 사례를 기억하므로써 학습을 한다. 그리고 유사도 측정을 사용해 새로운 데이터를 일반화한다.
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/12.png"/>
* 모델 기반 : 샘플들의 모델을 만들어 예측에 사용
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/13.png"/>
* 작업
데이터를 분석 → 모델 선택 → 훈련 데이터로 모델 훈련 → 새로운 데이터에 모델 적용해 예측(추론), 일반화가 잘 됐는지 확인
## 1.4 머신러닝의 주요 도전 과제
### :imp:나쁜 데이터 사례
* 충분하지 않은 양의 훈련 데이터
	* 알고리즘이 잘 작동하려면 데이터가 많아야 한다.
	* 복잡한 문제에서 알고리즘보다 데이터가 더 중요하다.
		`하지만 훈련 데이터를 모으는 것이 항상 쉽거나 저렴한 일이 아니기때문에 아직까지는 알고리즘을 무시하면 안된다.`
		
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/1.PNG" width = "500px"/>

> 데이터가 많을수록 정확도가 높아진다.

* 대표성 없는 훈련 데이터
	* 일반화가 잘되려면 우리가 일반화하기 원하는 새로운 사례를 훈련 데이터가 잘 대표하는 것이 중요하다.
	* 샘플링 잡음(우연에 의한 대표성 없는 데이터) : 샘플이 작을 때 생긴다.
	* 샘플링 편향 : 샘플 크기에 상관없이 표본 추출방법이 잘못될 때 생긴다.
		* 샘플링 편향 사례>
		랜던Randon과 루즈벨트Roosevelt가 경쟁했던 1936년 미국 대통령 선거에서Literary Digest 잡지사가 천만 명에게 우편물을 보내 수행한 대규모 여론조사로, 240만 명의 응답을 받았고 랜던이 선거에서 57% 득표를 얻을 것이라고 높은 신뢰도를 예측했다. 하지만 결과는 루즈벨트가 62% 득표로 당선되었다.
	
		* **예측이 잘못된 이유는?**
			1. 여론조사용 주소를 얻기 위해 전화번호부, 자사의 구독자 명부, 클럽 회원 명부 등을 사용 -> 이런 명부는 모두 "랜던"에 투표할 가능성이 높은 부유한 계층에 편중된 경향이 있다.
			2. 우편물 수신자 중 25% 미만의 사람이 응답 -> 이는 정치에 관심 없는 사람, Literary Digest를 싫어하는 사람과 다른 중요한 그룹을 제외시킴으로써 역시 표본을 편향되게 만들었습니다. (이러한 종류의 샘플링 편향을 '비응답 편향'이라고 한다,)
			<br/>
* 낮은 품질의 데이터
	*	훈련 데이터가 에러, 이상치, 잡음으로 가득하다면 머신러닝 시스템이 내재된 패턴을 찾기 어려워 잘 잘 작동하지 않을 것이다.
		* 일부 샘플이 이상치라는 게 명확하면 간단히 그것들을 무시하거나 수동으로 잘못된 것을 고치는 것이 좋다.
		* 일부 샘플에 특성 몇 개가 빠져있다면(예를 들면 고객 중 5%가 나이를 기록하지 않음), 이 특성을 모두 무시할지, 이 샘플을 무시할지, 빠진 값을 채울지(예를 들면 평균 나이로), 또는 이 특성을 넣은 모델과 제외한 모델을 따로 훈련시킬 것인지 등을 정해야 한다.
		 <br/>
* 관련 없는 특성
	* 훈련 데이터에 관련없는 특성이 적고 관련 있는 특성이 충분해야 시스템이 학습할 수 있을 것이다. 성공적인 머신러닝 프로젝트의 핵심 요소는 훈련에 사용할 좋은 특성들을 찾는 것. (이 과정을 **특성 공학**(feature engineering)이라 한다)
		*   **특성 선택**(feature selection) : 가지고 있는 특성 중에서 훈련에 가장 유용한 특성을 선택한다.
		*   **특성 추출**(feature extraction) : 특성을 결합하여 더 유용한 특성을 만든다.
		*   새로운 데이터를 수집해 새 특성을 만듭니다.
		<br/>
### :imp:나쁜 알고리즘 사례
* 훈련 데이터 과대적합
	* 과대적합 : 과도한 일반화로 ,모델이 훈련데이터에 너무 잘 맞지만 일반성이 떨어진다는 의미.
	* 훈련 데이터에 있는 잡음의 양에 비해 모델이 너무 복잡할 때 발생
		* 해결방법>
			-   파라미터 수가 적은 모델을 선택하거나(예를 들면 고차원 다항 모델보다 선형 모델), 훈련 데이터에 있는 특성 수를 줄이거나, 모델에 제약을 가하여 단순화시킨다.
			-   훈련 데이터를 더 많이 모은다.
			-   훈련 데이터의 잡음을 줄인다(예를 들면 오류 데이터 수정과 이상치 제거).
			
<img src = "https://github.com/gmksf99/Hands_On-Machin-Learning/blob/master/.img/3.PNG" width = "500px"/>

`고차원의 다항 회귀 모델이 삶의 만족도 훈련 데이터에 크게 과대적합된 사례, 이 모델이 선형 모델보다 잘 맞는다고 하더라도 실제로 이 예측은 믿기 힘들다.`
> 만약 위 모델에 관련없는 특성인 '나라이름'을 추가한다고 했을 때 이름에 'w'가 들어간 나라들의 만족도가 7보다 크다는 패턴을 감지할지 모른다.	이 패턴은 우연히 훈련 데이터에서 찾은 것이지만 진짜인지, 잡음 데이터로 인한 것인지 모델이 구분해낼 방법이 없다.

* 훈련 데이터 과소적합 
	* 과소적합 : 모델이 너무 단순해서 데이터의 내재된 구조를 학습하지 못할 때 발생.
		* 예시) 삶의 만족도 에 대한 선형 모델은 과소적합되기 쉽다.
			현실은 이 모델보다 더 복잡하다
		* **해결방법**>
			* 모델 파라미터가 더 많은 강력한 모델을 선택한다.
			* 학습 알고리즘에 더 좋은 특성을 제공한다.
			* 모델의 제약을 줄인다. (예를 들어 규제 하이퍼파라미터를 감소)

## 1.5 테스트와 검증
방법은 훈련 데이터를 **훈련 세트**와 **테스트 세트** 두개로 나누는 것이다.
* 일반화 오차 : 새로운 샘플에 대한 오류 비율
	* 테스트 세트에서 모델을 평가함으로써 이 오차에 대한 추정값을 얻는다.
	* 추정값은 이전에 본 적이 없는 새로운 샘플에 모델이 얼마나 잘 작동할지 알려줌
	* 예시) 훈련 오차가 낮지만 일반화 오차가 높다면 이는 모델이 훈련 데이터에 과대적합 되었다는 의미

일반화 오차가 5%인 모델을 만드는 최적의 하이퍼파라미터를 찾았다고 가정할 때 이 모델을 실제 서비스에 투입하면 성능이 예상만큼 좋지 않고 오차를 15%나 만든다 왜 그럴까?

* 일반화 오차를 테스트 세트에서 여러번 측정했으므로 모델과 하이퍼파라미터가 테스트 세트에 최적화된 모델을 만들었기 때문이다. 즉 모델이 새로운 데이터에 잘 작동하지 않을 수 있다는 의미이다.
*  **해결방법>**
	* 검증세트를 만든다 (교차 검증 기법 사용)
		1. 검증세트에서 최상의 성능을 내는 모델과 하이퍼파라미터를 선택한다
		2. 만족스런 모델을 찾으면 테스트 세트로 단 한 번의 최종 테스트를 한다.
	* 교차 검증 기법
		* 훈련 세트를 여러 서브넷으로 나누고 각 모델을 이 서브넷의 조합으로 훈련시키고 나머지 부분으로 검증한다.
		* 모델과 하이퍼파라미터가 선택되면 전체 훈련 데이터를 사용하여 선택한 하이퍼파라미터로 최종 모델을 훈련시키고 테스트 세트에서 일반화 오차 측정.
		
## 1.6 연습문제
1. 머신러닝 정의
	* 데이터로부터 학습할 수 있는 시스템을 만드는 것이다.
2. 머신러닝의 주요 도전 과제
	 *  부족한 데이터, 낮은 데이터 품질, 대표성 없는 데이터, 무의미한 특성, 훈련 데이터에 과소적합된 과도하게 간단한 모델, 훈련 데이터에 과대적합된 과도하게 복잡한 모델 등... 이다.
3. 사전 정보가 없는 여러 지형에서 로봇이 걸어가게 하려면 어떤 종류의 머신러닝 알고리즘을 사용하는가?
	* 환경을 관찰해서 행동을 실행하는 "강화 학습"을 사용한다.
4. 고객을 여러 그룹으로 분할 할 때 사용하는 알고리즘
	* 어떻게 정의할지 모른다면 비슷한 고객끼리 군집으로 나누기 위해 군집 알고리즘(비지도)을 사용한다.
	* 어떻게 정의할지 알고있다면 분류 알고리즘(지도)에 각 그룹에 대한 샘플을 주입한다.
6. 스팸 감지의 문제는 지도 학습인가 비지도 학습인가?
	* 지도 학습 문제이다. 알고리즘에 많은 이메일과 이에 상응하는 레이블이 제공된다.
7. 모델 파라미터와 학습 알고리즘의 하이퍼파라미터 사이에 차이점
	* 모델은 하나 이상의 파라미터를 사용해 새로운 샘플이 주어지면 무엇을 예측할지 결정한다.
	* 학습 알고리즘은 모델이 새로운 샘플에 잘 일반화되도록 이런 파라미터들의 최적 값을 찾는다. 하이퍼파라미터는 모델이 아니라 학습 알고리즘 자체의 파라미터이다.
8. 교차 검증이 무엇이고 왜 하나의 검증 세트보다 선호하는가?
	* 교차 검증은 검증 세트를 별도로 분리하지 않고 모델과 비교할 수 있는 기술이다. 훈련 데이터를 최대한 활용하도록 도와준다.
