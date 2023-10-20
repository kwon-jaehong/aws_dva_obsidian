

## 주제 :  API GateWay usage plans

API게이트웨이 사용량 계획

## 내용 

- API 키
	- 고객들에게 배포할 문자열(Key)
	- API gateway를 이용하기 위한 <mark style="background: #ADCCFFA6;">인증 토큰</mark>
	    - 클라이언트 헤더 변수 <mark style="background: #ADCCFFA6;">X-API-Key</mark> 에 API 키를 집어 넣는다


- 사용 계획
	- API키를 이용해 <mark style="background: #FFF3A3A6;">누가 언제 무엇을 호출 했는지 추적 가능</mark>
	- <mark style="background: #ADCCFFA6;">API 키 별, 요청/조절 제한 설정 가능함</mark>
	- <mark style="background: #FF5582A6;">API키, 스테이지 & 메서드, 사용량 조절을 연결해야 작동된다</mark>





- 실습
	- API Key, 사용계획은 API로 묶인다 -> 실습에서는 myfirstapi
	- 먼저 메서드 요청에서 API키 활성화를 True로 활성화 한다
		- ![[API GateWay usage plans-1.png]]
		- ![[API GateWay usage plans-2.png]]

 
 
	 - API KEY를 만들어 준다 (키 문자열 확인)
		 - ![[API GateWay usage plans-3.png]]
	 


	-  사용량 계획으로 들어가 셋팅을 해준다.
		- 스테이지 연결, API KEY를 연결 해줘야함
		- ![[API GateWay usage plans-4.png]]
		- ![[API GateWay usage plans-5.png]]
		- ![[API GateWay usage plans-6.png]]




	- 그리고 **`<중요>`** <mark style="background: #FF5582A6;">사용량 계획 -> 아래 빨간박스 조절 구성에서 세부 리소스를 지정해 줘야 연결된다</mark>
		- ![[API GateWay usage plans-7.png]]



	- API key 인증을 위한 호출 주소
		- ![[API GateWay usage plans-8.png]]








	- 포트스맨으로 API 키를  안 보낼 때 -> <mark style="background: #FF5582A6;">통신 실패</mark>
		- ![[API GateWay usage plans-9.png]]






	- 포트스맨으로 <mark style="background: #FFF3A3A6;">X-API-Key</mark> 헤더를 포함해 전달 -> 통신 성공(200코드)
		- ![[API GateWay usage plans-10.png]]







----


## 연결 문서







---

## 태그: #AWS, #DVA, #APIGateWay 






## 참고 링크




---
