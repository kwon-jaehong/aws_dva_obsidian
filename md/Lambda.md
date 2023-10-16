

## 주제 :  Lambda



## 내용 


- 람다함수 최대 실행 시간은 <mark style="background: #FF5582A6;">15분</mark>
- 람다 실행 RAM은 최대<mark style="background: #ADCCFFA6;"> 10GB</mark>까지 설정 가능
	- RAM을 높이면 <mark style="background: #ADCCFFA6;">CPU와 네트워크 품질도 높아짐</mark>
- 기본 람다 최대 동시 호출 수 = 1000개



- 람다 요금 정책
	- 람다 실행 시간
	- 람다 호출 횟수




- AWS CLI 람다 호출 명령문 예시
	- 동기식, 비동기식은 <mark style="background: #FF5582A6;">Invoke로 호출</mark>
	- invocation-type
		- RequestResponse(기본값) - 함수를 동기적으로 호출합니다.
		- Event - 비동기 호출
		- DryRun - 매개변수값 유효성 검사 및 함수 호출권한 확인
```bash
aws lambda invoke --function-name demo-lambda --cli-binary-format raw-in-base64-out --payload '{"key1": value}' --invocation-type Event --region -eu-west-1 response.json

```




- 람다 함수 핸들러
	- Lambda 함수의 <mark style="background: #ADCCFFA6;">핸들러</mark>는 이벤트를 처리하는 <mark style="background: #FFF3A3A6;">함수 코드의 메서드</mark>입니다
	- ![[Lambda-1.png]]




- 람다는 Execution context(<mark style="background: #FF5582A6;">실행 컨텍스트</mark>)가 있음
	- 실행 컨텍스트란?
		- <mark style="background: #FFF3A3A6;">다시 함수가 호출될 것을 예상하고, 람다의 일정시간 자원/환경이 유지</mark>
		- 즉, 짧은시간 <mark style="background: #ADCCFFA6;">여러번 호출하면 호출에 대한 컨텍스트를 재 사용함</mark>
		- 그래서 람다 함수 실행 (초기화)시간을 줄임





- 다음은 AWS Lambda 함수 작업에 대한 몇 가지 모범 사례입니다. 
- https://docs.aws.amazon.com/ko_kr/lambda/latest/dg/best-practices.html
	- 핵심 로직에서 Lambda 핸들러(진입점)를 분리합니다. 이를 통해 <mark style="background: #ADCCFFA6;">단위 테스트</mark>를 수행할 수 있는 더 많은 함수를 만들 수 있습니다.
	- 실행 컨텍스트(환경) 재사용을 활용하여 기능 성능을 향상시킵니다.
	- AWS Lambda 환경 변수를 사용하여 작동 매개변수를 함수에 전달합니다.
	- 함수 배포 패키지의 종속성을 제어합니다. 
	- 런타임 요구 사항에 맞게 배포 패키지 크기를 최소화합니다.
	- Lambda가 배포 패키지의 압축을 푸는 데 걸리는 시간을 줄입니다.
	- 종속성의 복잡성을 최소화하세요.
	- 재귀적인 코드 <mark style="background: #FFF3A3A6;">사용을 피하</mark>세요.



----


## 연결 문서

- [[Lambda authority |람다와 권한]]
- [[Lambda Concurrency |람다 동시성]]
- [[Lambda Asynchronous |람다 비동기]]
- [[Lambda monitoring |람다 모니터링]]
- [[Lambda VPC |람다 VPC]]
- [[Lambda ALB Integration |람다와 ALB통합]]
- [[Lambda eventmapping |람다 이벤트맵핑]]
- [[Lambda Layers |람다 레이어]]
- [[Lambda CloudFormation |람다와 클라우드포메이션]]
- [[Lambda CloudFront|람다 Edge 및 클라우드프론트]]
- [[Lambda alias & version |람다 버젼&별칭]]
- [[Lambda CodeDeploy |람다 코드디플로이 통합]]
- [[Lambda URLs|람다 URL]]
- [[Lambda etc|람다 기타]]


---

## 태그: #AWS, #DVA, #Lambda






## 참고 링크


---
