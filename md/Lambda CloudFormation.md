

## 주제 :  Lambda CloudFormation



## 내용 


- AWS 클라우드 포메이션에서 람다함수를 배포 가능 (	<mark style="background: #FF5582A6;">2가지</mark>  )
	- <mark style="background: #FFF3A3A6;">클라우드포메이션 코드 인라인 방식</mark>
		- 간단한 경우에만 사용
		- Code -> ZipFile에 실행 코드를 직접 업로드하는 타입 
		- 외부 종속성 파일을 업로드 불가
		- ![[Lambda CloudFormation-1.png]]










	- <mark style="background: #FFF3A3A6;">S3에 파일 업로드</mark>
		- ![[Lambda CloudFormation-2.png]]
		- S3Bucket - S3 버킷이름
		- S3Key - 버킷에서 zip파일 위치
		- S3ObjectVersion - S3에서 객체의 버전ID
		- ![[Lambda CloudFormation-3.png]]










- S3를 통해 다수 계정에 람다함수 배포 가능( 클라우드포메이션 통해서 )
	- 오리진 버킷의 정책을 설정해서 다른 계정에서 접근 가능
	- 또한 참조하는 곳에서 <mark style="background: #ADCCFFA6;">클라우드 포메이션이 실행될수 있게 권한을 허용 해야함</mark>
	- ![[Lambda CloudFormation-4.png]]




----


## 연결 문서







---

## 태그: #AWS, #DVA, #Lambda , #CloudFormation






## 참고 링크




---
