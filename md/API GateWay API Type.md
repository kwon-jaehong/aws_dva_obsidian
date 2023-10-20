

## 주제 :  API GateWay API Type



## 내용 

- API게이트웨이 생성할 때, 유형을 선택 할 수 있다.
	- ![[API GateWay API Type-1.png]]







- HTTP 타입
    - 저렴함
    - <mark style="background: #FFF3A3A6;">전부 프록시로 통합 됨</mark> (람다 프록시, HTTP 프록시)
	    - OIDC & Oauth2.0 인증, CORS 지원 
    - <mark style="background: #FF5582A6;">사용량 계획 및 API키 사용 못 함</mark>


- REST 타입
	- 다됨


![[API GateWay API Type-2.png]]





- WebSorcket 유형
	- 브라우저와 서버의 <mark style="background: #FFF3A3A6;">양방향 상호통신 유형</mark>, <mark style="background: #FFF3A3A6;">실시간 애플리케이션 유형</mark>
	- 클라이언트가 요청하지 않아도, 서버가 클라이언트에게 정보를 보냄
	- URL은 "<mark style="background: #FF5582A6;">wss</mark>://유니크-id.execute-api.리전.amazonaws.com/스테이지이름"
	- 클라이언트와 API게이트웨이가 통신을 할 수 있는 이유는 => <mark style="background: #FFF3A3A6;">커넥션 URL을 콜 백으로 계속 호출</mark>
		- 한 유저가 한 번 생성된 <mark style="background: #ADCCFFA6;">연결 URL</mark>을 계속 씀


	- 연결 , 메세지 전송, 연결 끊기 람다가 존재함
	- ![[API GateWay API Type-3.png]]
	- ![[API GateWay API Type-4.png]]

















----


## 연결 문서







---

## 태그: #AWS, #DVA, #APIGateWay 






## 참고 링크




---
