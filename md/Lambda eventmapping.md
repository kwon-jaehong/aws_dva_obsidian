

## 주제 :  Lambda eventmapping



## 내용 


- 키네시스 데이터 스트림, SQS, SNS FIFO, 다이나모 DB 스트림 등 -> <mark style="background: #FF5582A6;">람다가 이 리소스들을 사용하려면, 폴링 해야됨</mark>
    - 즉, 람다가 서비스에 레코드를 요청해야됨
    - 이 경우, 람다 내부에 <mark style="background: #FF5582A6;">이벤트 소스 맵핑이라는 큐</mark>가 생김
    - 이 경우, 람다 함수는 <mark style="background: #FF5582A6;">동기적으로 호출</mark>됨 (레코드를 받고 처리를 해야되니까)

![[Lambda eventmapping-1.png]]













- 이벤트 소스맵퍼 종류 2가지
	- 스트림 형식
		- <mark style="background: #FFF3A3A6;">키네시스 데이터 스트림, 다이나모DB 스트림 용</mark>
		- 병렬 처리를 사용하면, 샤드당 동시에 <mark style="background: #ADCCFFA6;">10개 배치</mark>까지 가능
		- 맵퍼는 각 샤드에 폴링을 생성함
		- 만약 배치(처리)에 <mark style="background: #ADCCFFA6;">에러가 날 경우, 영향 받는 배치는 중단됨</mark>
		- ![[Lambda eventmapping-2.png]]




	- 대기열 형식
		- SQS나 SNS FIFO용
		- 긴 폴링을 이용해 폴링 됨, <mark style="background: #FFF3A3A6;">배치 사이즈는 1~10</mark>
		- 람다가 처리하지 못한 메세지/아이템은 DLQ로 전달 가능, 람다용 DLQ는 <mark style="background: #FF5582A6;">비동기식 호출에만 작동됨</mark>
		- FIFO 대기열에서 <mark style="background: #ADCCFFA6;">활성 메세지 그룹(그룹ID기반)의 숫자와 람다 함수 실행 숫자는 같음</mark>
			- 표준 대기열은 다를 수 있음
		- ![[Lambda eventmapping-3.png]]






----


## 연결 문서







---

## 태그: #AWS, #DVA, #Lambda , #SQS, #SNS, #Kinesis






## 참고 링크




---
