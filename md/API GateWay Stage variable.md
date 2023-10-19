

## 주제 :  API GateWay Stage variable



## 내용 







- API게이트웨이 스테이지 배포에서 <mark style="background: #FF5582A6;">스테이지 변수값 (Stage variables)</mark>을 사용해, 배포를 바꾸지 않고도 환경 제어 가능
	- 스테이지 변수 사용 예
	    - 람다 ARN
	    - HTTP Endpoint 등
- 람다함수는 별칭마다 권한이 다름!!! -> <mark style="background: #FF5582A6;">각각, 람다 별칭과 API 스테이지간에 연결 필요</mark> 
- 스테이지 변수 포멧 => <mark style="background: #FFF3A3A6;">${stageVariables.변수이름}</mark>




- 스테이지 변수 실습
	- 아래 그림과 같이 람다 별칭 셋팅
		- ![[API GateWay Stage variable-1.png]]

 



 
	 - API 게이트웨이의 스테이지 변수로 람다 호출을 제어 할 수 있음(람다 별칭을 변수로 둠) => **apigateway1:${stageVariables.lambdaAlias}** => ${stageVariables.변수명}
		- ![[API GateWay Stage variable-2.png]]
	
 
 


 
 
 
	 - AWS CLI로 람다 함수 별칭 중 하나인 <mark style="background: #FF5582A6;">'v2v'</mark>에 <mark style="background: #ADCCFFA6;">API게이트웨이에서 람다호출에 대한 권한을 추가</mark>해줌 (권한을  별칭마다 주면, API 게이트웨이에서 별칭을 다 쓸 수 있음)
		 -  ![[API GateWay Stage variable-3.png]]







	 - API 테스트 할때 밑에 빨간 박스처럼 변수넣고 테스트 가능
		- ![[API GateWay Stage variable-4.png]]








	- 테스트와 다르게, 스테이지를 <mark style="background: #FF5582A6;">실 배포</mark>할때, 아래처럼 변수를 셋팅 해주면, 특정 람다 호출 가능
		- ![[API GateWay Stage variable-5.png]]








----


## 연결 문서







---

## 태그: #AWS, #DVA, #APIGateWay 






## 참고 링크




---
