

## 주제 :  Lambda external dependencies

람다 외부 종속성

## 내용 

- 실무에 런타임의 많은 패키지, 종속성을 사용할 때 추가 해야되는 요소
- 람다 코드 패키지 노압축 파일은 250MB 까지 지원
- 모든 패키지는 zip 파일로 압축 해야 됨
    - 패키지 크기가 <mark style="background: #FFF3A3A6;">50MB 이하면 람다 (콘솔)에서 바로 업로드 가능</mark>
    - 패키지 크기가 <mark style="background: #ADCCFFA6;">50MB 이상이면 S3에 올려 람다에서 참조</mark>
        - 이 경우, 람다가 S3 읽을 수 있는 IAM 역할 있어야 함

- AWS SDK는 모든 람다 환경에서 사용 가능 함 (= 따로 람다 컨테이너 환경에서 설치 안해도 됨)



----


## 연결 문서







---

## 태그: #AWS, #DVA, 






## 참고 링크




---
