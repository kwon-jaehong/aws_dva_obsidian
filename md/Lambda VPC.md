

## 주제 :  Lambda VPC



## 내용 

- <mark style="background: #FF5582A6;">람다는 기본적으로 VPC 외부에서 실행된다</mark>, 따라서 RDS나 엘라스틱 캐시에 접근 불가하다 => <mark style="background: #ADCCFFA6;">왜? 이런 AWS 리소스들은 VPC 내부에 있기 때문</mark>
	- 다이나모 DB는 VPC에 생성 되는게 아니라 접근 가능함


- 람다를 <mark style="background: #ADCCFFA6;">VPC내부에 실행할 수 잇게, 설정 가능</mark>하다
	- 람다 함수에 <mark style="background: #FF5582A6;">보안 그룹 및 서브넷을 배정</mark> 해야됨
	- 람다는 VPC안에서 사용하면 ENI를 생성하는데, 또한 <mark style="background: #FFF3A3A6;">AWSLambdaVPCAccessExecutionRole</mark> <mark style="background: #FF5582A6;">역할을 부여</mark>해야 된다.
	- ![[Lambda VPC-2.png]]



![[Lambda VPC-1.png]]




  

- 람다를 <mark style="background: #FF5582A6;">VPC 퍼블릭 서브넷에 배포해도 인터넷에 접근이 불가</mark>하다
	- <mark style="background: #ADCCFFA6;">NAT 게이트웨이/인스턴스를 사용해야 된다!</mark>
	- 람다가 VPC 내부에 있어도, CW 로그나 매트릭은 제대로 작동한다!
	- ![[Lambda VPC-3.png]]

  






----


## 연결 문서







---

## 태그: #AWS, #DVA, #Lambda 






## 참고 링크




---
