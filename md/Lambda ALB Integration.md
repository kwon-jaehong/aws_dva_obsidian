

## 주제 :  Lambda ALB Integration



## 내용 




- 사용자는 HTTP/S로 호출시,<mark style="background: #FF5582A6;"> ALB를 통해 람다 호출 가능함</mark>
- ALB -> 람다로 패킷이 갈때 HTTP정보가 Json 형태로 변환되서 감
	- ![[Lambda ALB Integration-1.png]]
	- ![[Lambda ALB Integration-2.png]]







- 반대로 람다 -> ALB로 반환될때, 정보가 변환되서 전달됨
	- ![[Lambda ALB Integration-3.png]]






- 멀티 헤더 값 전달도 가능함
	- ![[Lambda ALB Integration-4.png]]




----


## 연결 문서







---

## 태그: #AWS, #DVA, #Lambda , #ALB 






## 참고 링크




---
