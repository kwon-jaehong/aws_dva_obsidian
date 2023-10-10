

## 주제 :  EFS Mode



## 내용 

- EFS 성능 관련해서 아래와 같은 모드를 구성 할 수 있다.

	- Performance Mode (<mark style="background: #FF5582A6;">EFS 생성할때, 셋팅 가능</mark>)
		- General purpose (기본값)
			- 그냥 무난함
		- Max I/O 
			- 높은 레이턴시, 처리량, 병렬 처리시 사용하는 모드



	- Throughput Mode (처리량 모드)
		- Bursting
			- 버스트 크레딧을 사용해서 순간적으로 올림
			- 기본 1TB = 50MiB/s + 버스트 100MiB/s
		- Provisioned
			- <mark style="background: #FF5582A6;">미리 처리량을 지정</mark>
			- 예) 1TB 당 1GiB/s 처리량 증가 
		- Elastic 
			- <mark style="background: #FF5582A6;">워크로드를 예측할 수 없을 때 사용</mark>, 알아서 처리량이 확장 축소 됨
			- 읽기는 3GiB/s, 쓰기는 1Gib/s 









----


## 연결 문서







---

## 태그: #AWS, #DVA, #EFS







## 참고 링크




---
