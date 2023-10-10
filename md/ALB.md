

## 주제 :  ALB



## 내용 

- 레이어 7에서 작동함
- ALB는 <mark style="background: #FF5582A6;">IP가 유동적으로 바뀜</mark>
- HTTP/2, WebSocket, <mark style="background: #FF5582A6;">gRPC</mark> 프로토콜 지원
- HTTP -> HTTPS 리다이렉트 지원
- 지원 라우팅 종류
	- 경로 라우팅 지원
		- 예) example.com/user 와 example.com/posts 라우팅
	- 호스트네임의 URL 라우팅 지원
		- 예) one.example.com 와 two.example.com
	- 쿼리 문자열, 헤더 문자열 지원
		- 예) example.com/users?id=124&order=false
- port 맵핑 기능이 있음, MSA에서 유용하게 쓰이는 로드밸런서 유형
	- 컨테이너 포트 8080을 80번 포트로 매핑해서 진행 가능함
- <mark style="background: #FF5582A6;">EIP을 할당 할 수는 없음</mark>
- 여러 타깃 그룹에 라우팅 가능함 (다수 타깃)
	- EC2,ASG,ECS 등
	- Private IP주소에 대해 할당 가능
- ALB를 통해 들어온 클라이언트 정보는, Ec2에서 확인할 때 헤더에 삽입 되어있음
	- <mark style="background: #FF5582A6;">X-Forwarded-For</mark> : 클라이언트 접속 IP
	- <mark style="background: #FF5582A6;">X-Forwarded-Port</mark> : 클라이언트 접속 Port
	- <mark style="background: #FF5582A6;">X-Forwarded-Proto</mark> : 클라이언트가 사용한 프로토콜




----


## 연결 문서







---

## 태그: #AWS, #DVA, #ELB, #ALB






## 참고 링크




---
