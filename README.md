# k8s101
### 101이란
>"원-오-원"이라 읽는다. 본래 미국에서 대학 간의 학부과정을 손쉽게 비교하기 위하여 주단위로 표준번호를 부여하는 체계에서 비롯했는데, 여기서 맨 앞번호는 난이도나 학위수준을, 뒤따르는 번호는 해당 전공분야 내의 주제나 단계를 나타낸다. 즉 101은 난이도 1 + 01 단계를 의미하는 것으로, 말인즉 일반적으로 입문수업을 뜻하게 됐다. 예컨대 Art 101이라면 미술을 기초부터 배우는 것이다. - 출처 나무위키
### 쿠버네티스 란
컨테이너를 사용하다보면 여러가지의 컨테이너를 사용해야 되는 상황이오고 이것들을 관리하는 부분이 쉽지 않기 때문에 오케스트레이션을 하기 위해 나온 툴입니다.
docker-compose 도 계속 발전하고 있지만 한계가 명확하고 클러스터 단위로 관리를 하기에는 지금은 쿠버네티스가 가장 최선(아마도 이제는 유일무이)입니다.

문서는 쿠버네티스 공식 문서를 보는것을 추천드리고 여기서는 실습 위주의 101을 해보려고 합니다.

[쿠버네티스 공식 문서](https://kubernetes.io/docs/home/)

![Kubernetes Cluster](https://d33wubrfki0l68.cloudfront.net/2475489eaf20163ec0f54ddc1d92aa8d4c87c96b/e7c81/images/docs/components-of-kubernetes.svg)

101 이 아닌 어려운길을 가시려면 아래의 kubernetes the hard way를 추천 드립니다.

[Kubernetes the hard way](https://github.com/kelseyhightower/kubernetes-the-hard-way)