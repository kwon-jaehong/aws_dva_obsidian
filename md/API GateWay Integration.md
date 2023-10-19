

## 주제 :  API GateWay Integration



## 내용 


- <mark style="background: #FFF3A3A6;">API GateWay 통합이란?</mark>  리소스 -> 메서드를 설정하고, 어떤 것을 연결하는지 결정하는 것
	- ![[API GateWay Integration-1.png]]









- APIGateWay 통합 타입
	- <mark style="background: #FFF3A3A6;">MOCK 타입 </mark>
		-  MOCK란? -> 실제품을 만들어 보기 전, 디자인 검토를 위해 실물과 비슷하게 만든 시제품을 통칭해서 부르는 말
		- 백엔드 소스(람다나 커스텀 HTTP 등)에<mark style="background: #ADCCFFA6;"> 요청을 전송하지 않고도 응답을 반환 시킴</mark>
		- 개발 / 테스트에서 쓰이고, 프로덕션 레벨에서는 쓰이지 않음



	- <mark style="background: #FFF3A3A6;">AWS 타입</mark>
		- AWS Lambda 함수, AWS HTTP 엔드포인트 또는 AWS Step Functions와 같은 AWS 서비스를 호출할 수 있습니다.
		- 요청 및 응답 변환 [[API GateWay Mapping Template|매핑 템플릿]]을 설정하여 <mark style="background: #FF5582A6;">클라이언트 요청 및 백엔드 서비스 응답을 변환</mark>하거나 조작할 수 있습니다.



	 - <mark style="background: #FFF3A3A6;">AWS_PROXY</mark> 타입 ( = 람다 프록시라고도 부름 )
		- 람다 통합에 과정을 <mark style="background: #FFF3A3A6;">간소화한 설정</mark>
		- 간단하게 요청을 전달하고 <mark style="background: #FF5582A6;">거의 변환 없이 백엔드 서비스로 전송하는 데 사용</mark>
		- <mark style="background: #FF5582A6;">람다만 가능</mark>, 기본적으로 Json형식으로 출력을 반환함




	- <mark style="background: #FFF3A3A6;">HTTP</mark>
		- 클라이언트 요청과 <mark style="background: #ADCCFFA6;">백엔드 HTTP 서비스 간에 요청 및 응답 변환 및 로직을 추가하고 제어하는 데 사용</mark>
		-  HTTP 사용자 지정 통합은 <mark style="background: #FF5582A6;">요청과 통합 응답을 둘 다 설정</mark>해야 합니다. 메서드 요청에서 통합 요청으로, 그리고 통합 응답에서 메서드 응답으로 필수적인 <mark style="background: #FF5582A6;">데이터 매핑을 설정</mark>해야 합니다.





	- <mark style="background: #FFF3A3A6;">HTTP_PROXY</mark>
		- 단순히 클라이언트 요청을 백엔드 HTTP 서비스로 프록시로 전달하는 간단한 방식으로 사용














----


## 연결 문서

- [[API GateWay Mapping Template |APIGateWay 맵핑템플릿]]






---

## 태그: #AWS, #DVA, #APIGateWay 






## 참고 링크

- https://docs.aws.amazon.com/ko_kr/apigateway/latest/developerguide/api-gateway-api-integration-types.html


---
