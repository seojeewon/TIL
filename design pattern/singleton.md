# 싱글톤 패턴
클래스의 인스턴스가 `1개`만 생성

```java
public class Singleton{
    private static Singletone INSTANCE = new Singleton();

    private Singleton(){}

    public static Singleton getInstance(){
        return INSTANCE;
    }
}
```

## 장점
1. 메모리 낭비 방지
   
2. 다른 클래스들이 데이터 공유 가능

## 단점
1. 테스트하기 어렵다.
   - TDD->단위테스트->각 테스트가 독립적이어야 함
   - 싱글톤 인스턴스는 전 테스트에 영향 받을 수 있고, 이후 테스트에 영향 줄 수 있다.

2. 의존도가 높아진다.

3. 자식 클래스를 만들 수 없다. (부모의 생성자가 `private`)

### 언제 사용
- 데이터베이스 커넥션풀
- 스레드풀
- 캐시