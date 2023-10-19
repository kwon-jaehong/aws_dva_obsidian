

## 주제 :  API GateWay security


API GateWay 인증 및 권한 부여

## 내용 


-  아래 방법들을 통해 <mark style="background: #FF5582A6;">API에 대한 액세스를 제어할 수 있음</mark>



- IAM을 통한 인증 & 권한 부여
	- IAM 자격증명은, <mark style="background: #FFF3A3A6;">헤더에 있는 sig v4 기능을 활용해 인증</mark>
	- <mark style="background: #ADCCFFA6;">authentication(인증)은 IAM</mark> , <mark style="background: #ADCCFFA6;">authorization(권한부여)는 IAM 정책</mark>
	- 아래 그림은 클라이언트에서  API 게이트웨이로 정보 전달 -> IAM -> API 게이트웨이는 IAM 정책을 체크하고 맞으면 람다 호출
	- ![[API GateWay security-1.png]]




	- API게이트웨이 리소스 정책을 통한 <mark style="background: #ADCCFFA6;">교차 계정 엑세스</mark>도 가능
		- ![[API GateWay security-2.png]]




- Cognito 활용 인증
	- API 게이트웨이는 코그니토를 통해, <mark style="background: #FFF3A3A6;">사용자의 신분을 검사</mark> 함
	- 코그니토는 사용자의 수명주기를 관리 (토큰 관리, 수명주기, 자동교체 등)
	- 인증은 <mark style="background: #ADCCFFA6;">Cognito User Pools</mark>, 권한부여는 <mark style="background: #ADCCFFA6;">API게이트웨이 매소드</mark>
	- 아래 그림 기준으로, 클라이언트는 코그니토에 인증 및 <mark style="background: #FFF3A3A6;">토큰을 리턴</mark>받고, 토큰을 API 게이트웨이로 전송, API 게이트웨이는 코그니토와 통신해서 <mark style="background: #FFF3A3A6;">토큰 유효성 검사</mark> -> 통과하면 백엔드 호출
	- ![[API GateWay security-3.png]]





- 람다 Authorizer(권한 부여자)
	- 특정 토큰, 문자열, 쿼리 등을 <mark style="background: #FF5582A6;">인증람다</mark> 를 구성해서 검사
		- <mark style="background: #FFF3A3A6;">커스텀 권한 부여</mark>를 위함,  <mark style="background: #FFF3A3A6;">가장 유연한 방식 </mark>
	- 인증방식 2가지 예시
		-  토큰 기반 - <mark style="background: #FFF3A3A6;">OAuth 또는 SAML과 같은 전달자 토큰 인증 전략을 사용하는 사용자 정의 인증 체계를 구현하려는 경우에만 적합</mark>
		- 특정 파라미터 값을 기반
	- 인증에 성공하면, 람다는 유저에게 IAM 정책을 반환하고, 정책은 캐시 됨
	- 인증은 외부나 람다 커스텀으로 진행 , 권한 부여는 람다가 부여해줌
	- ![[API GateWay security-4.png]]









- 람다 및 코그니토의 API제어  (권한 부여자) 콘솔 화면
	- ![[API GateWay security-5.png]]





- 리소스 정책 (IAM, IAM 정책 기반) 제어 예시
	- AWS 계정 허용 목록 템플릿 정책 코드
		- ![[API GateWay security-7.png]]







	- IP 번위 거부 목록 템플릿 정책 코드 예시
		- ![[API GateWay security-6.png]]











	- 소스 VPC 허용 목록 정책 코드 예시
		- ![[API GateWay security-8.png]]












----


## 연결 문서







---

## 태그: #AWS, #DVA, #APIGateWay , #보안, #cognito







## 참고 링크




---
