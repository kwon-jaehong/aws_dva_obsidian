

## 주제 :  ASG Policies - 오토스케일링 정책



## 내용 


- Dynamic Scaling  - 동적 스케일링

	 - TargetTracking Scaling - 대상 추적 스케일링
		- 가장 단순한 스케일링
		- 예)  Ec2 평균 CPU 40% 유지로 알아서 수량 맞춰

  
	- Simple / Step Scaling - 심플 / 스탭 스케일링
		- 메트릭의 트리거 방식
		- 예) CPU 70% 이상이면, <mark style="background: #FF5582A6;">Ec2 2개 추가,</mark> <mark style="background: #FF5582A6;">30%이하면 1개 삭제</mark>
	
		
	- Scheduled Actions - 예약된 작업
		- 예) 금요일 오후 5시에 Ec2 2대 늘리기


- Predictive Scaling - 예측 스케일링
	- 머신러닝 예측 모델로 스케일링 진행 (전략을 내가 세우진 안음)




- 스케일링 Cooldown (쿨다운)
	- ASG에서 스케일링 작업이 끝날 때 마다 쿨다운(휴지기간)을 가짐, <mark style="background: #FF5582A6;">추가/삭제되는 인스턴스가 서비스 실행, 종료 시간을 기다려주는 행위라고 보면 됨</mark>
	- 쿨다운이 차기 전까지는 <mark style="background: #FF5582A6;">ASG에서 인스턴스를 추가,종료는 하지 못함</mark>
		- 예) ASG에서 인스턴스 1개를 추가함 -> 추가된 인스턴스는 서비스 실행까지 1분 정도 걸림 -> 쿨다운이 없으면 ASG에서 추가된 인스턴스가 서비스를 제공하지 않는다고 판단 -> 추가된 인스턴스 삭제,  무한 반복 
	- 
	- 쿨다운의 기본값 300초 (6분)
	- 오토스케일링 그룹이 1초마다 관찰을 할 순 없음
	- ASG는 쿨다운 기간에는 아무일도 안 함






----


## 연결 문서







---

## 태그: #AWS, #DVA, #ASG






## 참고 링크




---
