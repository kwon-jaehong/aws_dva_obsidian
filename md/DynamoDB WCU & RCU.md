

## 주제 :  DynamoDB WCU & RCU



## 내용 


- 다이나모DB에는 <mark style="background: #FF5582A6;">초당 읽기/쓰기에 용량이 제한</mark>되어 있고, 이를 설정하는 모드가 따로 존재함
	- <mark style="background: #FFF3A3A6;">프로비저닝 모드</mark>
	    - <mark style="background: #FF5582A6;">오토 스케일링 지원</mark>
	    - 미리 자원을 지정, 지정해둔 용량보다 넘어서도 <mark style="background: #FF5582A6;">burst capacity(버스팅 용량)으로 일시적으로 사용</mark> 가능함
	        - 버스팅 용량이 다 소진되면, <mark style="background: #FF5582A6;">ProvisionedThroughputExceededException</mark> 에러 발생함 (프로비저닝 처리량 초과 예외)
	
	- <mark style="background: #FFF3A3A6;">온디멘드 모드</mark>   
	    - 읽기 쓰기 모드가 <mark style="background: #FF5582A6;">자동으로 업/다운</mark>
	    - 쓰는 만큼 나옴 (프로비저닝 모드 2.5배 <mark style="background: #ADCCFFA6;">비쌈</mark>)
- 24시간 마다 프로비저닝 , 온디맨드 <mark style="background: #FF5582A6;">모드를 바꿀 수 있음</mark>

![[DynamoDB WCU & RCU-1.png]]








- <mark style="background: #FF5582A6;">반올림!!!!</mark>

### WCU (Write Capacity Units) / 쓰기 모드
- 초당 1KB 데이터 쓰기 = 1 용량
	- WCU 계산 예 
		- 초당 1KB 쓰기 = 1용량
		- 초당 1.5KB는 올림하여 2용량 사용







### RCU (Read Capacity Units) / 읽기 모드
- 초당 4KB 데이터 읽기 (강력한 일관된 읽기 모드 기준) = 1용량
- 읽기모드는 2가지 있음
	- <mark style="background: #FFF3A3A6;">Eventually Consistent Read (최종적 일관된 읽기 모드) - 기본값</mark>
	    - 다이나모DB에서 데이터를 쓰기 후, 분산된 다이나모 DB에 복제가 진행 안 되었을 경우 <mark style="background: #FF5582A6;">데이터를 못 읽을 수도 있음</mark> (데이터를 쓰고 100ms내 읽기 상황, 즉 DB 동기화 업데이트가 안되서 발생하는 오류)


	 - <mark style="background: #FFF3A3A6;">Strongly Consistent Read (강력한 일관된 읽기 모드)		</mark>    
		    - 방금 막 쓴 데이터를 읽을 경우 사용
		    - <mark style="background: #FF5582A6;">다이나모DB API에서 ConsistentRead라는 변수 = True로 둬야 함</mark>
			    - 강력한 읽기는 2번 읽는 방식임	

- RCU 계산 방법 예
![[DynamoDB WCU & RCU-2.png]]





- 파티션 분배
	- 다이나모DB는 검색전, <mark style="background: #FF5582A6;">파티션키는 해시 함수를 통해 분산 된다</mark>
	- RCU와 WCU는 파티션 수에 걸쳐 고르게 분배됨
![[DynamoDB WCU & RCU-3.png]]




- 처리량 관련 에러
	- <mark style="background: #FF5582A6;">ProvisionedThroughputExceededException</mark> 문구로 에러 발생
	        
	    - 원인
	        - 핫 키 (파티션 키)
	        - 핫 파티션
	        - 아주 큰 아이템(항목) -> <mark style="background: #FF5582A6;">RCU와 WCU 보다 넘는 많은 아이템들을 쓰기/읽기 작업</mark>을 하려는 경우
	    
	  - 해결법	        
		- 지수 백오프 전략 사용
		- 파티션키를 최대한 많이 분산해서 구성
		- 읽기 작업일 경우, DAX (DynamoDB Accelerator) 사용





----


## 연결 문서







---

## 태그: #AWS, #DVA, #DynamoDB 






## 참고 링크




---
