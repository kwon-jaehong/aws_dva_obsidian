

## 주제 :  API GateWay consol1


API 게이트웨이 실습 1

## 내용 



- API게이트웨이는 람다함수에 <mark style="background: #ADCCFFA6;">29초 시간초과 자동으로 걸림(기본값)</mark>
![[api_실습1.png]]





- API게이트웨이에서 <mark style="background: #FFF3A3A6;">리소스</mark>란 개념은 Path같은 개념이다

![[api_실습2.png]]










- 리소스 -> 메서드를 구성하면 다음과 같이 4가지 항목이 구성 가능하다
	- ![[API GateWay consol1-1.png]]


	- 매서드 요청
		- 메서드 요청은 클라이언트가 API 엔드포인트에 요청을 보낼 때 요청을 수신하고 처리하는 부분
		- IAM 인증 여부, API키 여부, 필요한 쿼리,HTTP 헤더 등 <mark style="background: #FF5582A6;">클라이언트가 보내온 정보를 검사함</mark>
		- 특정 쿼리 문자열 매개변수를 포함하도록 <mark style="background: #ADCCFFA6;">요청을 강제하거나 API 캐싱을 활성화</mark> 함
		- ![[API GateWay consol1-2.png]]


	- 통합 요청
		- API Gateway -> 백엔드 서비스로 전달하기 전 <mark style="background: #FF5582A6;">요청을 변환하고 전달하는 방법을 정의</mark> ([[API GateWay Mapping Template|매핑템플릿]])
		- 클라이언트 요청을 요구 사항에 맞게 변환하거나, 필요한 추가 정보를 요청에 추가할 수 있음
		- ![[API GateWay consol1-3.png]]



	- 통합 응답
		- 백엔드 -> API Gateway 전달하기 전에 처리하는 부분
		- [[API GateWay Mapping Template|매핑템플릿]]을 이용해서 내용 수정 가능함
		- ![[API GateWay consol1-4.png]]



	- 메서드 응답
		-  응답 상태 코드, 헤더, 응답 본문의 구성 및 매핑을 정의
		- 이를 통해 클라이언트가 올바른 응답을 받을 수 있도록 응답을 조작하거나 변환
		- ![[API GateWay consol1-5.png]]








----


## 연결 문서







---

## 태그: #AWS, #DVA, #APIGateWay 






## 참고 링크




---
