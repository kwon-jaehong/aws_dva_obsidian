

## 주제 :  Lambda Concurrency



## 내용 

  

- 람다는 리전당, 총 최대 1000개까지 동시 실행될 수 있다. (이를 <mark style="background: #ADCCFFA6;">람다 동시성</mark>이라 한다)
	- AWS 서비스 쿼터 요청해서 1000개 보다 더 높게 설정도 가능함

- 람다 함수 수준에서 동시성을 설정 할 수 있다 (아래그림 참조)
	- ![[Lambda Concurrency-1.png]]

- 동시성을 제어하지 않으면, 같은 리전의 다른 람다 서비스에 <mark style="background: #FF5582A6;">Thottle</mark> 에러가 발생한다
	- ![[Lambda Concurrency-2.png]]



- 예약되지 계정의 <mark style="background: #FF5582A6;">동시성은 최소 100이하로 내려 갈 수 없음</mark>
	- 즉, 계정에서 동시성을 할당받지 못한 함수에 대해서 -> <mark style="background: #FF5582A6;">동시성 100개 자리는 무조건 확보해 두고 있는것</mark>
	- 예
		- 내 계정에서 10개의 람다함수가 있고, 첫번째 함수에 동시성 400개 부여, 두번째 함수에 동시성 200개 부여
		- 이때 세번째 함수에는 동시성을 최대 300개 까지 밖에 할당 못함
		- 왜냐면 <mark style="background: #ADCCFFA6;">나머지 7개 함수들이 100개 공간으로 돌려써야 함</mark>



- 비동기 호출 + 람다 동시성 한계를 실행하면, <mark style="background: #FF5582A6;">람다 내부 이벤트 대기열에서 최대 6시간에 걸쳐, 람다를 실행 하려고 함</mark>, 재시도 간격은 지수 백오프 방식으로 증가



- 람다 동시성 한계 에러 코드 2가지
	- 스로틀링 에러 429
	- 시스템 에러 500 시리즈


- <mark style="background: #FFF3A3A6;">람다의 콜드 스타트</mark>
	- 새로운 람다 함수 인스턴스를 생성할 때, 이를 <mark style="background: #FF5582A6;">'초기화'</mark>라고 한다
		- 만약 대규모 람다 함수 초기화가 발생할 경우, 코드 종속성이나 기타 작업 때문에 오랜 시간이 걸릴 수 있다
		- 이럴때 프로비저닝된 동시성을 사용하면, 해결 가능
	- 함수가 호출 되기전에, 동시성을 미리 할당 해 놓음
	- 프로비저닝된 동시성은 람다의 최신버전이으로실행 불가능
  
  

  
  




----


## 연결 문서







---

## 태그: #AWS, #DVA, #Lambda 






## 참고 링크




---