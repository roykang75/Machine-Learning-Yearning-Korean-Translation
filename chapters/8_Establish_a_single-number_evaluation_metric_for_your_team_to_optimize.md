## 8. Establish a single-number evaluation metric for your team to optimize

분류의 정확도는 단일숫자(single-number) 평가 지표의 한 예이다: 개발 데이터셋에 대해서 분류 알고리즘을 수행하고, 얼마만큼의 부분 데이터가 제대로(올바르게) 분류 되었는지에 대하여 단일숫자를 얻게 된다. 이 단일숫자로 표현되는 평가지표에 따르면, 만약 분류 알고리즘 A가 97%의 정확도를 얻고 B가 90%의 정확도를 얻는다면, A가 B보다 더 나은 알고리즘이라고 판단할 수 있다.

이와 대조적으로, Precision 과 Recall은 단일숫자 평가지표가 아니다: 3개 숫자의 2개 집합으로 분류 알고리즘을 평가하게 된다. 복수개의 평가지표를 가지는 것은 알고리즘의 비교를 더 어렵게 만든다. 다음과 같이 알고리즘의 성능이 나왔다고 가정해 보자.

<div style="text-align=center">
  <img src="../img/8_1.PNG"/>
</div>

위와 같은 경우에는 두개의 분류 알고리즘 모두 명확하게 누가 더 좋다라고 말할 수 없다. 그렇기 때문에, 뭐를 선택해야 하는지 즉각적인 판단이 어렵다고 볼 수 있다.

<div style="text-align=center">
  <img src="../img/8_2.PNG"/>
</div>

개발 과정에서, 당신의 팀이 모델 파라메터, feature 선택 방법, 알고리즘의 설계등에 대하여 수 많은 아이디어를 시도할지도 모른다. 정확도와 같은 단일숫자 평가지표는 모든 모델을 손쉽게 더 나은 순으로 정렬할 수 있게 해주고, 가장 좋은 알고리즘을 빠르게 선택하는데 도움을 준다.

만약, Precision과 Recall을 정말로 고려해야 한다면, 이 두개를 단일숫자로 결합하는 표준적인 방법을 사용하는 것을 추천한다. 예를 들어서, 이 두가지 지표의 평균으로 단일숫자를 만들어낼 수 있다. 또한, 다른 대안으로 평균을 구하는 약간 변형된 방법인 "[F1 스코어](https://en.wikipedia.org/wiki/F1_score)" 라는 값을 계산할 수도 있겠다 (F1 스코어는 단순 평균보다 더 좋다고 알려져 있다).

<div style="text-align=center">
  <img src="../img/8_3.PNG"/>
</div>

단일숫자 평가지표는 많은 분류 알고리즘 중 하나를 선택해야 하는 경우, 의사결정의 시간을 많이 단축시켜준다. 각 알고리즘의 선호도에 따른 순위를 매기고, 이후 진행되어야 하는 방향에 대하여 깔끔한 제시/가이드를 해준다.

마지막 예제로, 고양이 그림 분류 알고리즘의 정확도를 4개의 시장(미국, 중국, 인도, 그외)에 대해 별도로 추적한다고 가정해 보자. 이때, 결과로는 4가지 평가 지표를 얻게 된다. 4가지 숫자의 그냥 평균값 또는 가중된 평균값을 계산하여, 단일숫자 평가지표를 얻을 수 있다. 가중된 평균값을 계산하는 것은 이러한 환경에서 가장 보편화된 방법으로 알려져 있다.
