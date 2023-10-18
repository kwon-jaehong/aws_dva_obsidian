

## 주제 :  Lambda CloudFront



## 내용 

- 기본 람다 함수는 <mark style="background: #FFF3A3A6;">리전에 배치되어 실행</mark>된다. 하지만 엣지 위치에 콘텐츠를 배포 및 람다 함수를 써야하는 경우 아래와 같은 람다를 쓸 수 있다.
	- 람다 Edge 함수는 전역적(서울,오하이오 등) 으로 배포됨 






- CloudFront에서 사용할 수 있는 함수는 <mark style="background: #FFF3A3A6;">2가지</mark> 이다
	- <mark style="background: #ADCCFFA6;">CloudFront Function</mark>
	    - 자바스크립트 기반의 가벼운 함수, 초당 수백만개 수행 가능
	    - <mark style="background: #ADCCFFA6;">Viewer</mark>의 요청/응답만 바꾸는데 사용
	        - 예시) URL이나 헤더, 쿠키의 속성 변경 등 캐시키 최적화에 특화됨
	        - 인증 요청 가능 (삽입된 JWT 토큰 검증)
	    - 최대 함수 실행시간 1ms
	    - ![[Lambda CloudFront-1.png]]





	- <mark style="background: #ADCCFFA6;">Lambda@Edge</mark>
	    - 노드 JS나 파이썬 기반의 함수, 초당 1000개 까지 처리 가능
	    - <mark style="background: #FFF3A3A6;">us-east-1 에서 함수 작성</mark>, 그럼 모든 지역에 함수가 복제 됨
	    - 뷰어 요청/응답, 오리진 요청/응답 다 적용 가능
	        - 예시) 파일 시스템 엑세스해서 HTTP 본문 가져오기 등
	    - 최대 함수 실행시간 10초
	    - ![[Lambda CloudFront-2.png]]






![[Lambda CloudFront-3.png]]







----


## 연결 문서







---

## 태그: #AWS, #DVA, #Lambda , #CloudFront, #Edge 






## 참고 링크




---
