# Redis
메모리 기반의 `키-값` 저장소(`NoSQL`)
- 다양한 `자료구조` 지원
  - string
  - list
  - hash
  - sorted set

## Redisson
Redis `자바` 라이브러리

### 분산락
내부적으로 Redis의 `Pub/Sub` 메커니즘 활용

1. 락 획득
   - 클라이언트 A가 락 획득 요청
   - Redisson이 해당 락이 다른 클라이언트에 의해 획득되었는지 확인

2. Pub/Sub을 통한 락 경합
   - 락이 이미 획득되었다면 Redisson은 `Pub/Sub` 채녈을 사용하여 `대기열을 구독`한다.

    - 클라이언트 B, C도 락을 획득하기 위해 요청

    - Redisson은 이런 요청을 채널을 통해 수신하고, 이 요청들을 대기열에 추가

3. 락 해제
   - 락을 해제할 때 Redis에 전달
   - Redisson은 이 정보를 받고 Pub/Sub채널을 통해 대기열의 다른 클라이언트에게 알림

