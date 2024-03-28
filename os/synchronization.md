# 동기화
키워드: `#실행순서`, `#상호배제`, `#임계 구역`, `#레이스 컨디션`
## 정의
프로세스 간의 수행 시기를 맞춘다.
- `실행 순서` 제어: 프로세스를 올바른 순서대로 실행
- `상호 배제`: 동시에 접근하면 안되는 자원에 대해 `하나`의 프로세스만 접근

```
동기화
    ├── `실행 순서 제어`하는 동기화
    │ 
    ├── `상호 배제`를 위한 동기화
```

### 동기화가 필요한 이유
프로세스의 `실행 순서`와 `자원의 일관성`을 보장하기 위해

## 공유 자원과 임계 구역
- 공유 자원: 프로세스들이 공유하는 공동의 자원
- 임계 구역: 공유 자원에 접근하는 코드 중 동시에 실행하면 문제가 발생하는 영역

## 레이스 컨디션(Race Condition)
여러 프로세스가 동시 다발적으로 `임계 구역`의 코드를 실행하여 문제가 발생하는 경우
- 데이터의 `일관성` 깨짐

### 레이스 컨디션이 발생하는 이유
- 컴퓨터는 저급 언어를 실행하기 때문에 여러 줄의 저급 언어로 변환된 고급 언어 한 줄을 실행하는 과정에서 문맥 교환이 발생 가능

### 3가지 해결 원칙(상호 배제를 위한 동기화를 위한 원칙)
1. `상호 배제`(mutual exclusion): 한 프로세스가 임계 구역에 진입하면 다른 프로세스는 임계 구역에 들어올 수 없다.
2. `진행`(progress): 임계 구역에 아무 프로세스도 진입 X -> 진입하고자 하는 프로세스는 들어갈 수 있어야 함.
3. `유한 대기`(bounded waiting): 한 프로세스가 임계 구역에 진입하고 싶으면, 걔는 언젠가 임계 구역에 들어올 수 있어야 함. (=임계 구역에 들어가기 위해 무한정 대기하면 안된다.)



[다음: 동기화 기법](sync_technique.md)