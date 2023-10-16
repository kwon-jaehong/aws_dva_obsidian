

## 주제 :  Lambda authority



## 내용 


- 람다는 생성하면, 클라우드워치에 로그를 보내야 한다. 그래서 함수를 생성하면 클라우드 워치에 대한 쓰기 권한이 자동적으로 부여된다. ( <mark style="background: #FF5582A6;">AWSLambdaBasicExecutionRole</mark> )
	- ![[Lambda authority-2.png]]


- 다이나모 DB에 연결하려면, <mark style="background: #FF5582A6;">AWSLambdaDynamoDBExecutionRole</mark>정책을 부여하면 된다.
	- ![[Lambda authority-1.png]]

- 다른 <mark style="background: #FFF3A3A6;">AWS 서비스</mark>에 연결하려면 클라우드 와치 + <mark style="background: #FFF3A3A6;">다른 AWS 서비스 권한 </mark>을 설정 해주면 된다.



----


## 연결 문서







---

## 태그: #AWS, #DVA, #Lambda 






## 참고 링크




---
