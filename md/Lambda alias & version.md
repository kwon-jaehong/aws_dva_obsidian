

## 주제 :  Lambda alias & version



## 내용 


- 람다 함수의 Version
	- 현재 작업중인 람다는 <mark style="background: #FFF3A3A6;">$LATEST로 게시되며, 코드변경 가능</mark>
	- 함수를 게시/배포하면, <mark style="background: #FF5582A6;">(샘플)버젼 V1으로 배포가 되며, 코드,환경변수 등 변경은 불가능해짐</mark>
	- 람다의 <mark style="background: #ADCCFFA6;">버젼별 각각 다른 ARN(아마존 리소스 네임)을 가짐</mark>
	- ![[Lambda alias & version-1.png]]





- 람다 별칭
	- 람다 별칭은 최종 사용자에게, <mark style="background: #FF5582A6;">안정적인 엔드 포인트를 제공하기 위함</mark>
	- 람다 별칭은 [[Distribution method |블루/그린 배포도]] 가능하다 (+ 가중치 트래픽도 가능함)
	- 람다 별칭도 <mark style="background: #ADCCFFA6;">각각 다른 ARN(아마존 리소스 네임)을 가짐</mark>
	- 별칭은 다른 별칭을 참조 할 수 없음
	- ![[Lambda alias & version-2.png]]












----


## 연결 문서







---

## 태그: #AWS, #DVA, #Lambda 






## 참고 링크




---
