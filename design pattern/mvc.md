# MVC 패턴
키워드: `#Model`, `#View`, `#Controller`

애플리케이션을 `Model`, `View`, `Controller` 세 부분으로 나눈 것.

## Model
데이터 다루고, 비즈니스 로직 처리
- 데이터 `CRUD` 트랜잭션

## View
사용자 인터페이스

## Controller
`Model`과 `View` 사이에 있는 컴포넌트로 `Model`이 데이터를 어떻게 처리해야 하는지 알려줌.
- 클라이언트 요청 -> 데이터 가공해서 모델 호출->요청받은 데이터 뷰에 전달