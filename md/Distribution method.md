

## 주제 :  Distribution method (서비스  배포 방식)



## 내용 



### 서비스 배포 방식


![[Distribution method-5.png]]








1. All at Once (한번에 모두)
	- 기존 서비스를 종료하고, 새 버전 배포 
	- 서비스 <mark style="background: #FF5582A6;">다운타임이 발생</mark>하고, 추가 요금(장비 프로비저닝)가 없음
	- <mark style="background: #FF5582A6;">무중단 배포가 아님!</mark>
	- ![[Distribution method-1.png]]








2. Rolling
	- 업데이트시, 초기에 설정한 인스턴스 용량내에서 조금씩(사용자 설정 - 10% 5% 등) 서비스를 바꿈
	- 추가 요금(장비 프로비저닝) 없고, 배포 완료 시간이 <mark style="background: #FF5582A6;">느림</mark>
	- <mark style="background: #ADCCFFA6;">서비스 다운 타임 없음</mark>
	- ![[Distribution method-2.png]]







3. Rolling with additional batches
	- Rolling배포 + 장비를  추가로 프로비저닝해서 배포 진행
	- 서비스 다운타임 0
	- ![[Distribution method-3.png]]








3. Immutable (불변)
	- 배포에 필요한 <mark style="background: #ADCCFFA6;">임시 ASG를 만들어</mark> v2 배포 <mark style="background: #ADCCFFA6;">(원래 인스턴스 용량 2배)</mark>
	- 새 인스턴스가 상태 확인을 통과할 때까지 <mark style="background: #ADCCFFA6;">새 버전과 기존 버전이 함께 트래픽을 처리</mark>
	- 서비스 다운타임 0, <mark style="background: #FF5582A6;">배포 시간이 가장 김</mark>
	- 새 버전 장애 발생시, 이전 버전에 대한 <mark style="background: #FF5582A6;">가장 빠른 롤백 제공</mark>
	- ![[Distribution method-4.png]]





4. Blue / Green
	- AWS Beanstalk에서 <mark style="background: #ADCCFFA6;">직접 제공하는 기능이 아님</mark>
	- Route53과 함께 사용하고, <mark style="background: #ADCCFFA6;">수동 배포</mark> 해야 됨
	- <mark style="background: #FFF3A3A6;">Immutable와 특성이 비슷하지만</mark>, <mark style="background: #FF5582A6;">차이점은 새 버전의 진입점의(로드밸런서 , DNS) 교체</mark>
	- ![[blue-green-deployment-4787416bca99a5dd28577d99caa44340.gif]]




5. Traffic Splitting (카이나리 배포, 트래픽 분할)
	- 로드밸런서를 통해 현 버전, 새 버전사이의 트래픽 분산 확인
	- 블루그린 방법에서 발전된 방법
	- ![[Distribution method-6.png]]













----


## 연결 문서







---

## 태그: #AWS, #DVA, #배포방법






## 참고 링크

- https://llshl.tistory.com/47
- https://docs.aws.amazon.com/ko_kr/elasticbeanstalk/latest/dg/using-features.deploy-existing-version.html




---
