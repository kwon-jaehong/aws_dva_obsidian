

## 주제 :  API GateWay cache



## 내용 


- API게이트웨이에서 <mark style="background: #ADCCFFA6;">응답을 캐시로 줄 수 있다</mark>
   - 백엔드 호출의 수를 줄임 -> 과부하/스로틀링 에러에 효과적


- <mark style="background: #ADCCFFA6;">캐시 활성화/비활성화가 자유롭다</mark>
	- 캐시 활성화는 <mark style="background: #FF5582A6;">스테이지 > 메서드 별 적용 가능</mark>
	- 캐시의 TTL은 <mark style="background: #FFF3A3A6;">0초 ~ 최대 1시간</mark> (기본값 300초)
- 캐시는 비싸기 때문에, 프로덕션 환경에서 쓰는게 좋음
- 캐시는 암호화 가능하며, 0.5GB ~ 237GB까지 캐시 용량이 정해진다


- 클라우드프론트처럼 <mark style="background: #FFF3A3A6;">캐시 무효화</mark>도 가능
    - <mark style="background: #FF5582A6;">"header.Cache-Control:max-age=0" </mark>를 클라이언트에서 전달하면 됨
    - 단, APIGateWAY에 IAM 정책이 있어야 함 => <mark style="background: #FF5582A6;">"execute-api:InvalidateCache"</mark>
    - ![[API GateWay cache-1.png]]









- 실습
	- 먼저, 스테이지(전체)에서 캐시 활성/비환성 및 캐시 용량 설정
		- ![[API GateWay cache-2.png]]


 
 
	 - 이 후, 매서드별 캐시 활성화 설정 (스테이지 캐시 설정 -> 메서드 별 캐시 설정이 요구 된다) 
		 - ![[API GateWay cache-3.png]]














----


## 연결 문서







---

## 태그: #AWS, #DVA, #APIGateWay 






## 참고 링크




---
