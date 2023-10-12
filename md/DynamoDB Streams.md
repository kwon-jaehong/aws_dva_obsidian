

## 주제 :  DynamoDB Streams



## 내용 

- <mark style="background: #FFF3A3A6;">스트림 테이블</mark>을 만들고, 기본 테이블의 항목 업데이트,삽입,삭제가 기록됨
	- 스트림 데이터 보존기간은 <mark style="background: #FF5582A6;">최대 24시간</mark> (24시간이 초과된 데이터는 언제든지 삭제될 수 있음)
	- 샤드로 구성되고, 키네시스 데이터 스트림과 유사함
	- 스트림 테이블을 따로 <mark style="background: #ADCCFFA6;">프로비저닝 안해도 됨</mark> -> AWS가 알아서 함


- 스트림 활성화하면, 테이블의 <mark style="background: #FF5582A6;">모든 데이터/항목 적용</mark>(특정 데이터/항목 <mark style="background: #ADCCFFA6;">선택 적용 안됨</mark>)`


- 스트림 데이터 보낼 수 있는곳
	- 람다
	- 키네시스 데이터 스트림
	- KCL 어플리케이션(키네시스 클라이언트 라이브러리)



- 스트림 활성화 보기 옵션 (아래 그림 참조)
	- KEYS_ONLY
	- NEW_IMAGE
	- OLD_IMAGE
	- NEW_AND_OLD_IMAGES
	- ![[DynamoDB Streams-1.png]]





----


## 연결 문서







---

## 태그: #AWS, #DVA, #DynamoDB 






## 참고 링크




---
