

## 주제 :  Auto Scaling Group



## 내용 


- Ec2 인스턴스의 장비를 자동 생성 및 삭제 등, <mark style="background: #FF5582A6;">관리 자동화를 위함</mark> 
- 로드밸런서와 통합되어, 추가 및 삭제되는 노드를 ASG에서 알아서 로드밸런서에 등록 취소 해줌
- ASG에 <mark style="background: #ADCCFFA6;">Launch Template - 시작 템플릿</mark>와 <mark style="background: #FF5582A6;">Launch Configurations - 시작 구성</mark>형태가 있지만, <mark style="background: #FF5582A6;">시작 구성은 이제 안씀</mark> => 시작 템플릿 으로 ASG 구성

![[Auto Scaling Group-1.png]]



- ASG 인스턴스 새로 고침 (refresh)
- 일종의 롤 아웃 배포라고 보면됨 (비율 정해서 롤아웃으로 배포됨 74강 1분 그림 참조)





----


## 연결 문서


- [[ASG consol | ASG 콘솔화면]]
- [[ASG Policies | ASG 정책]]




---

## 태그: #AWS, #DVA, #ASG






## 참고 링크




---
