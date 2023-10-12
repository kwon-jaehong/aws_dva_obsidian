

## 주제 :  DynamoDB globalindex & localindex



## 내용 




### 로컬 보조 인덱스 (Local secondary Index - LSI)

- 테이블에 <mark style="background: #ADCCFFA6;">대체 정렬키</mark>를 설정 (추가적인 정렬키를 설정하는 행위임)
	- 테이블당 최대 5개 설정가능
- <mark style="background: #FF5582A6;">반드시 테이블 생성 시점에 정의 해야됨</mark>, 생성되고 나서는 수정 불가능
- 보조 테이블 개념이 아니기 떄문에, <mark style="background: #FF5582A6;">다이나모DB에 성능상 문제 없음</mark>
- 예시
	- 아래 그림은 Game_TS 기반으로 쿼리를 하지 못함 (프라이머리키가 아님)
	- 이때, <mark style="background: #FF5582A6;">기존 Game_TS 속성을 로컬 보조인덱스로 지정하면 쿼리 가능해짐</mark>
	- ![[DynamoDB globalindex & localindex-1.png]]
	- ![[DynamoDB globalindex & localindex-2.png]]





### 글로벌 보조 인덱스 (Global Secondary Index - GSI)

- 기본 테이블에서 다른 파티션키와 정렬키를 가질 수 있음 -> <mark style="background: #FF5582A6;">기본 테이블에서 내 설정(키설정)에 맞게 새롭게 테이블을 만드는 것</mark> 
- <mark style="background: #FF5582A6;">기본 테이블의 항목이 추가/업데이트/삭제 되면, GSI도 같이 수정됨</mark> 
- 사용하기 위해 <mark style="background: #ADCCFFA6;">RCU와 WCU를 프로비저닝 해줘야 함</mark> (새로운 테이블을 만드는 행위이기 때문에)
	- 기본 테이블 생성 후,  <mark style="background: #ADCCFFA6;">GSI 생성이나 삭제 가능</mark>
	- ![[DynamoDB globalindex & localindex-3.png]]

- 이 GSI 테이블에 <mark style="background: #FF5582A6;">쓰로틀링 에러(처리량 에러)가 걸리면</mark>, <mark style="background: #FFF3A3A6;">메인 테이블도 쓰로틀링 걸림</mark>





----


## 연결 문서







---

## 태그: #AWS, #DVA, 






## 참고 링크




---
