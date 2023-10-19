

## 주제 :  API GateWay Canary



## 내용 


- API게이트웨이 변경 사항에 관해 <mark style="background: #FF5582A6;">소량의 트래픽으로 테스트 방법</mark>

- 실습
	- 먼저 카나리아 배포를 활성화 함
		- ![[API GateWay Canary-1.png]]

 
 
 


	 - dev 스테이지를 배포할 때, 카라리아 사용을 체크하고 배포함
		- ![[API GateWay Canary-2.png]]

 
 
 
 
 
 
	 - 절반 확률로 트래픽이 분산 됨
		- ![[API GateWay Canary-3.png]]





 
	 - 로그랑 모니터링 결과 이상 없으면, 카이나리 승격
		- ![[API GateWay Canary-4.png]]
	


----


## 연결 문서







---

## 태그: #AWS, #DVA, #APIGateWay , #배포방법 






## 참고 링크




---
