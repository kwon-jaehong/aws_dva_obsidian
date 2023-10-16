

## 주제 :  Lambda monitoring



## 내용 


- 람다는 [[Lambda authority |기본적으로 CW와 통합되서]],  로그, 메트릭은 클라우드워치에 저장됨
	- 람다 메트릭 -  호출 수, 기간, 동시실행, 오류률, 스로틀 등 제공
	- 람다 로그 - 람다의 로그들



- 람다에서는 X-Ray를 이용한 추적이 가능함 (<mark style="background: #ADCCFFA6;">Active Tracing 활성화</mark>만 해주면 됨)
	- ![[Lambda monitoring-1.png]]

	- x-ray IAM 역할도 추가는 해줘야 함 ( <mark style="background: #ADCCFFA6;">AWSXRAYDaemonWriteAccess</mark> )

	- <mark style="background: #FFF3A3A6;">X-ray 관련 람다 대표 환경변수 (3가지)</mark>
		- \_X_AMZN_TRACE_ID  ( 컨테이너 추적 헤더 )
		- AWS_XRAY_CONTEXT_MISSING  (기본값은 LOG_ERROR)
		- AWS_XRAY_DAEMON_ADDRESS  ( x-ray 데몬의 IP 주소:포트 )




----


## 연결 문서







---

## 태그: #AWS, #DVA, #Lambda , #CloudWatch






## 참고 링크




---
