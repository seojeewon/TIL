# 객체 지향 설계의 5대 원칙
키워드: `#SOLID`, `#SRP`, `#OCP`, `#LSP`, `#ISP`, `#DIP`

객체 지향 설계의 5대 원칙은 간단하게 `SOLID`로 말할 수 있다.

## `S`RP : Single Responsibility Principle
> 단일 책임 원칙

하나의 모듈은 하나의 책임만 진다. </br>
→ 모듈이 변경되는 이유는 한 가지

- 변경이 필요할 때 수정이 필요한 대상이 명확해진다

## `O`CP : Open-Closed Principle
> 개방 폐쇄 원칙

확장에는 열려있고,
- 모듈의 확장성 보장(기능추가)

수정에 대해 닫혀있다.
- 객체를 직접적으로 수정하는 것은 제한

### 추상화
다형성과 확장을 가능케하는 객체지향의 장점을 극대화하는 설계 원칙
- 기능 추가할 때 상속 관계에 맞춰 추가한다.


## `L`SP : Liscov Substitution Principle
> 리스코프 치환 원칙

올바른 상속 관계.

하위타입은 언제나 상위타입으로 교체될 수 있다. </br>
→ 부모 클래스의 인스턴스 자리에 자식 클래스의 인스턴스를 대신 사용했을 때 코드가 원래 의도대로 동작해야 한다.
- 부모 클래스와 자식 클래스의 행위에는 일관성이 있어야 한다.

### 다형성
부모클래스의 의도와 다르게 자식클래스에서 메서드를 재정의하면 LSP 위반

## `I`SP : Interface Segregation Principle
> 인터페이스 분리 원칙

클라이언트의 용도와 목적에 적합한 인터페이스를 제공

## `D`IP : Dependency Inversion Principle
> 의존 역전 원칙

객체에서 어떤 class를 참조해서 사용해야 할 때, 그 class를 직접 참조하는 것이 아니라 상위요소를 참조한다.
- 하위모듈이 자주 수정되면 상위모듈이나 클라이언트도 자주 수정해야 하기 때문

참고 </br>
[[1] 완벽하게 이해하는 SRP (단일 책임 원칙)](https://inpa.tistory.com/entry/OOP-%F0%9F%92%A0-%EC%95%84%EC%A3%BC-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EB%8A%94-SRP-%EB%8B%A8%EC%9D%BC-%EC%B1%85%EC%9E%84-%EC%9B%90%EC%B9%99)


[[2] 완벽하게 이해하는 OCP (개방 폐쇄 원칙)](https://inpa.tistory.com/entry/OOP-%F0%9F%92%A0-%EC%95%84%EC%A3%BC-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EB%8A%94-OCP-%EA%B0%9C%EB%B0%A9-%ED%8F%90%EC%87%84-%EC%9B%90%EC%B9%99)

[[3] 완벽하게 이해하는 LSP (리스코프 치환 원칙)](https://inpa.tistory.com/entry/OOP-%F0%9F%92%A0-%EC%95%84%EC%A3%BC-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EB%8A%94-LSP-%EB%A6%AC%EC%8A%A4%EC%BD%94%ED%94%84-%EC%B9%98%ED%99%98-%EC%9B%90%EC%B9%99)

[[4] 완벽하게 이해하는 ISP (인터페이스 분리 원칙)](https://inpa.tistory.com/entry/OOP-%F0%9F%92%A0-%EC%95%84%EC%A3%BC-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EB%8A%94-ISP-%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4-%EB%B6%84%EB%A6%AC-%EC%9B%90%EC%B9%99)

[[5] 완벽하게 이해하는 DIP (의존 역전 원칙)](https://inpa.tistory.com/entry/OOP-%F0%9F%92%A0-%EC%95%84%EC%A3%BC-%EC%89%BD%EA%B2%8C-%EC%9D%B4%ED%95%B4%ED%95%98%EB%8A%94-DIP-%EC%9D%98%EC%A1%B4-%EC%97%AD%EC%A0%84-%EC%9B%90%EC%B9%99)