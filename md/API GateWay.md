

## 주제 :  API GateWay



## 내용 




- API 키를 생성해, 클라이언트 요청의 스로틀링을 핸들링 할 수 있다. 
- API Gateway로 생성된 모든 API는 **HTTPS** 엔드포인트만 노출
	- **https**://_{restapi_id}_.execute-api._{region}_.amazonaws.com/_{stage_name}_/ 형식을 지켜야함
	- http://779protaw8.execute-api.us-east-1.amazonaws.com/tutorialsdojo/ <- 안됨 (HTTPS가 아니니까)


- API GateWay는 계정 제한은 <mark style="background: #FF5582A6;">초당 만번 콜</mark>이다.
    - AWS 서비스 쿼타로 늘릴 수 있음
    - <mark style="background: #FF5582A6;">API중 하나가 과하게 사용되면, 다른 API도 스로틀링에 영향을 받음 (람다와 같음)</mark>
        - 예) 하나의 계정에서 A,B라는 API가 있을 경우 A+B 합쳐서 초당 만번 콜 이상나면 오류남




- API 게이트웨이 AWS 배포/운영 방식 (3가지)  
    - <mark style="background: #FFF3A3A6;">Edge-optimized (기본값)</mark>
		- 글로벌 배포
		- <mark style="background: #FFF3A3A6;">클라우드 프론트 엣지 위치를 통해 요청을 라우팅함</mark>
		- 실질적 배포는 <mark style="background: #FFF3A3A6;">한 리전에 배포한 소스가 엣지 로케이션에 다 복사되는 방식</mark>
		- ACM으로 HTTPS 인증을 사용하려면, <mark style="background: #ADCCFFA6;">인증서는 us-east-1에 있어야</mark> 함

	- <mark style="background: #FFF3A3A6;">Regional</mark>
		- 클라우드 프론트 위치 사용 X, 한 지역 배포
		- 클라우드 프론트를 연동하면 에지-옵티마이저랑 똑같지만, <mark style="background: #FFF3A3A6;">캐싱전략과 클라우드 프론트를 더 많이 제어 가능해짐</mark>
		- ACM으로 HTTPS 인증을 사용하려면, <mark style="background: #ADCCFFA6;">인증서는 동일 리전에 있어야함</mark>

	- <mark style="background: #FFF3A3A6;">Private</mark>
		- VPC 프라이빗 서브넷에 내부용으로 배포
		- ENI를 사용해 VPC 내부에서만 접근 가능 => 퍼블릭이 아님




    
- API게이트웨이 인증 방식    
    - 유저 기반 인증
        - IAM 역할
            - 내부 어플리케이션 인증용
        - 코그니토
            - 웹,모바일 어플리케이션 외부 사용자 인증용
        - 커스텀
            - 사용자가 직접 인증방식 짤수도 있음



- APIGateWay를 동작 시키려면, 배포를 무조건 해야 됨`
- ACM으로 인증서를 사용할 경우, 반드시 <mark style="background: #FF5582A6;">Route 53에 CNAME이나 A-별칭으로 레코드를 설정 해야 됨</mark>
    - 배포는 스테이지 타입으로 관리됨  (몇개 든 상관없음)
    - 배포하지 않으면, 작동 안 함





- API 게이트웨이 에러 종류


    - <mark style="background: #FF5582A6;">400번대</mark> (클라이언트 오류) - API게이트웨이 진입할 때 오류이거나 API 할당량 오류
        - 400 : 잘못된 요청
        - 403 : Access Denied, WAF 필터링
        - 429 : Quota exceeded, Throttle -> <mark style="background: #ADCCFFA6;">클라이언트 할당량 초과</mark>


    - <mark style="background: #FF5582A6;">500번대 (서버오류)</mark> - 잘못된 주소, 응답, 타임아웃 등 전반적인 리소스 문제임
        - <mark style="background: #ADCCFFA6;">502</mark> : Bad Gateway -> 서버가 게이트웨이나 프록시 서버 역할을 하면서 업 스트림 서버로부터 유효하지 않은 응답을 받았다는 것을 의미
            - <mark style="background: #FF5582A6;">람다 프록시 통합이나, 백엔드에서 응답을 안 함</mark>
        - <mark style="background: #ADCCFFA6;">503</mark> : 서버가 요청을 처리할 준비가 되지 않은 것을 의미
        - <mark style="background: #ADCCFFA6;">504</mark> : 통합 장애 또는 타임아웃 (API 게이트웨이 <mark style="background: #FFF3A3A6;">기본 타임아웃은 29초</mark>)


	- APIGateWay는 일반적으로 JSON 형식이 기본이지만, Lambda 함수가 XML 형식으로 반환되는 경우에는 API Gateway가 제대로 처리하지 못할 수 있습니다. 

----


## 연결 문서

- [[API GateWay consol1 |API GateWay 기본 실습]]
- [[API GateWay API Type |API GateWay API 유형]]
- [[API GateWay Stage |API GateWay 스테이지 & 실습]]
- [[API GateWay Canary |API GateWay 카이나리 배포]]
- [[API GateWay Integration |API GateWay 통합 타입]]
- [[API GateWay cache |API GateWay 캐쉬]]
- [[API GateWay security |API GateWay 인증 및 권한부여]]
- [[API GateWay usage plans |API GateWay 사용량 계획]]
- [[API GateWay monitoring |API GateWay 로깅 및 모니터링]]
- [[API GateWay CORS |API GateWay CORS]]




---

## 태그: #AWS, #DVA, #APIGateWay






## 참고 링크




---
