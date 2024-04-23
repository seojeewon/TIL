# IN 연산
여러 개의 값을 비교.

IN 연산자에 입력된 값 중 `하나라도 일치`하는 것이 있으면 리스트에 조회됨

### 예제
```SQL
SELECT *
FROM TABLE_A
WHERE NAME IN ('JOHN', 'JENNY', 'JACK')
```

# NOT IN 연산
`IN()`에 있는 값은 제외하고 조회됨

## 서브쿼리
IN/NOT IN 연산자 안에 `서브쿼리` 사용 가능