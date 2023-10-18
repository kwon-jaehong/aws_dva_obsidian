

## 주제 :  Lambda URLs



## 내용 


- 람다를 URL로 호출 가능한 기능 (ipv4와 ipv6 지원)
- 활성화는 사용자 마음 (기본값은 URL 생성 안되있음)
- 인터넷을 통해 URL 엑세스 가능, <mark style="background: #ADCCFFA6;">프라이빗 링크 통해서 URL 호출 불가능</mark>
- 람다 URL은 함수의 특정 버전이나 설정 불가능, <mark style="background: #FF5582A6;">무조건 $LATEST로 적용 가능</mark>
- CORS 구성도 가능





![[Lambda URLs-1.png]]

![[Lambda URLs-2.png]]







- 람다 URL 보안
	- 람다를 URL로 호출할 때, 보안 설정 가능
	- 정책문서에 <mark style="background: #ADCCFFA6;">lambda:FunctionUrlAuthType</mark> 타입을 적어둠
		- None - 인증 안함, 누구나 람다를 호출 할 수 있음
		- AWS_IAM - 람다 호출 대상은 <mark style="background: #FF5582A6;">lambda:InvokeFuntionURL</mark> 권한을 가지고 있어야함
	- 람다 호출 대상이 <mark style="background: #FFF3A3A6;">같은</mark> AWS 계정이라면, AWS ID기반 <mark style="background: #FFF3A3A6;">or</mark> 리소스기반 정책이 허용 되어 있어야함 
	- 람다 호출 대상이 <mark style="background: #FFF3A3A6;">다른</mark> AWS 계정에서 발생하면, 람다 제공측에서 ID기반 정책 <mark style="background: #FFF3A3A6;">and</mark> 함수 호출쪽에서 리소스기반 정책이 허용 되어 있어야함
	- ![[Lambda URLs-3.png]]




















----


## 연결 문서







---

## 태그: #AWS, #DVA, #Lambda , #보안






## 참고 링크




---
