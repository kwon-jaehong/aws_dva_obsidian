

## 주제 :  API GateWay Mapping Template



## 내용 

- 맵핑 템플릿이란?
    - <mark style="background: #ADCCFFA6;">요청/응답의 정보를 수정하는 템플릿</mark>
    - VTL(Velocity Template Language)를 사용해서 if,for 등 조건문 실행 가능
    - 콘텐츠 유형을 application/json 또는 application/xml로 설정
        - SOAP API와 REST API를 기반으로 한다는 말임
        - SOAP API => XML 기반
        - REST API => JSON 기반
    - 예) 쿼리 파라미터의 이름 수정, body 수정, 헤더 추가 등
    - 아래 그림은 백엔드가 SOAP API이며, 들어오는 정보는 REST API(JSON)이다. 그래서 API Gateway에서 정보를 변환을 (JSON <-> SOAP) 맵핑 템플릿을 사용해서 변환해준다.

![[API GateWay Mapping Template-1.png]]








- 실습
	- 먼저, 람다함수의 리턴값은 json타입이다 ( "test" : "mapping test" )
		- ![[API GateWay Mapping Template-2.png]]
	



 
	 - 맵핑 적용 전, APIGateWay 메서드 테스트 화면
		 - ![[API GateWay Mapping Template-3.png]]

 





	 - 아래 그림과 같이 통합 응답을 클릭하고, 맵핑을 application/json, Key값을 바꾸는 예시를 작성한다
		 - ![[API GateWay Mapping Template-4.png]]
		 - ![[API GateWay Mapping Template-5.png]]

 
 




 
	 - 맵핑 적용 후, 테스트를 해보면 반환되는 키값이 test -> mapping으로 수정되어 리턴 되어진다.
		 - 물론 key와 value 모두 수정 가능함
		- ![[API GateWay Mapping Template-6.png]]


















----


## 연결 문서







---

## 태그: #AWS, #DVA, #APIGateWay 






## 참고 링크




---
