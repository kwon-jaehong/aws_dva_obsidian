

## 주제 :  DynamoDB



## 내용 

- 완전 관리형 서비스, <mark style="background: #ADCCFFA6;">NoSQL 기반이기에 SUM, AVG 등 집계 연산 불가능</mark>
- 다이나모DB도 스탠다드, <mark style="background: #FF5582A6;">Infreequent Access(IA)</mark> -> 두 가지 테이블 클래스가 있음
- DB에서 데이터의 최대 크기는 <mark style="background: #FF5582A6;">400KB</mark> 


- Primary Key (기본키) 구성
	- 파티션키
		- 해쉬 전략을 쓰고, 아이템(행 데이터)의 <mark style="background: #FF5582A6;">유니크한 값</mark>	
	 - 정렬키
		 - 파티션키와 조합하여, 기본키를 생성
	 - 강의 화면 예시
		 - ![[DynamoDB-1.png]]
		- ![[DynamoDB-2.png]]

- 테이블에 정렬키가 있으면, 파티션 키 데이터가 같아도 상관 없음
	- 즉, 컴퓨터 입장에서 <mark style="background: #FF5582A6;">기본키가 구별만 가능하면</mark> <mark style="background: #ADCCFFA6;">키 값이 중복되어도 상관 없다</mark>는 뜻




----


## 연결 문서

- [[DynamoDB consol1 | DynamoDB 만들기 실습 ]]
- [[DynamoDB globalindex & localindex | DynamoDB 로컬 보조 인덱스 & 글로벌 인덱스]]
- [[DynamoDB WCU & RCU]]
- [[DynamoDB Streams]]
- 







---

## 태그: #AWS, #DVA, #DynamoDB






## 참고 링크




---
