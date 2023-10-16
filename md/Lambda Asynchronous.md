

## 주제 :  Lambda Asynchronous



## 내용 


- 비동기 호출은 결과를 알 수 없음(<mark style="background: #FF5582A6;">람다 호출만 하고 결과는 안 봄</mark>)
- 비동기식은<mark style="background: #FF5582A6;"> 이벤트 큐에서 람다가 읽어서 처리함</mark> (대규모 처리에 유리)
	- S3, SNS, 클라우드 와치등이 있다
	- 이벤트 브릿지 cron Job, Code Commit의 이벤트

- 비동기 호출은 <mark style="background: #FF5582A6;">총 3번 함수를 실행 시도 함</mark> (성공 할 때까지)
	- 첫번째는 바로시도, 두번째는 1분뒤, 세번쨰는 2분뒤

- 람다가 실패하면 SQS나 SNS로 DLQ를 구성해서 작업 내역 보낼 수 있음



![[Lambda Asynchronous-1.png]]








- S3 이벤트를 다이렉트로 받으면, 비동기식 호출로 진행된다
	- s3 이벤트는 <mark style="background: #FF5582A6;">실시간이 아니다</mark>, 때때로 1분정도 걸리기도 한다
	- 그리고 s3셋팅에 버저닝을 활성화 해야된다!
- S3에 같은 파일 동시 작업이 진행될 경우, <mark style="background: #FF5582A6;">하나의 이벤트(최신 버젼) 밖에 받지 못함</mark>


![[Lambda Asynchronous-2.png]]


## 연결 문서







---

## 태그: #AWS, #DVA, #Lambda 






## 참고 링크




---
