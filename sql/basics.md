# 기본 9가지 문법 정리

- [기본 9가지 문법 정리](#기본-9가지-문법-정리)
  - [1. ORDER BY](#1-order-by)
  - [2. GROUP BY / COUNT](#2-group-by--count)
    - [COUNT](#count)
    - [GROUP BY](#group-by)
  - [3. WHERE / AND / OR](#3-where--and--or)
  - [4. CASE WHEN / ELSE](#4-case-when--else)
  - [5. LIKE / NOT LIKE](#5-like--not-like)
  - [6. 서브쿼리](#6-서브쿼리)
  - [7. JOIN](#7-join)
  - [8. OUTER JOIN](#8-outer-join)
  - [9. SUM / MIN / MAX / AVG](#9-sum--min--max--avg)

## 1. ORDER BY
`정렬`할 때 사용
- 가장 `마지막`에 사용
- `ORDER BY` + `정렬하고 싶은 컬럼명`
- DEFAULT: 오름차순
- 내림차순: `ORDER BY` + `컬럼명` + `DESC`
- 여러 컬럼으로 정렬하고 싶으면 `,`로 나열
  - ex) 거래가 오래된 순으로 아파트 연, 월, 일
  ```sql
  SELECT *
  FROM apt_list
  ORDER BY year, month, day
  ```

## 2. GROUP BY / COUNT
### COUNT
건수를 알아볼 때 씀
```sql
SELECT count(*)
FROM apt_list
//apt_list의 행의 개수
```
- `COUNT`는 `GROUP BY`와 같이 자주 쓰인다!

### GROUP BY
전체 데이터가 아닌 `특정 항목`의 개수, 평균 등을 확인하기 위함
- 중복을 제거할 때도 사용 가능

ex) 이번 달/ 연도별 아파트 매매 건수

```sql
//동별 아파트 매매 건수
SELECT dong, count(*)
FROM apt_list
GROUP BY dong
```
```sql
//연도별 아파트 매매 건수
SELECT year, count(*)
FROM apt_list
GROUP BY year
```

## 3. WHERE / AND / OR
테이블의 `일부` 데이터만 보고 싶을 때 사용
```sql
//삼성동의 아파트 매매 건수
SELECT *
FROM apt_list
WHERE dong='삼성동'
```

## 4. CASE WHEN / ELSE
데이터 값이 `특정 조건`일 때 다르게 표현
```sql
CASE WHEN 조건 1 THEN 표현 1
     WHEN 조건 2 THEN 표현 2
     ELSE 기타표현
     END
```
```sql
SELECT price, year, month, day, nm,
      , CASE WHEN price <= 10000 THEN '1억 이하'
      WHEN price <= 30000 THEN '1억~3억 이하'
      WHEN price > 30000 THEN '3억 초과'
      END
FROM apt_list
```

## 5. LIKE / NOT LIKE
- LIKE : 특정 단어 조건 포함
- NOT LIKE : 특정 단어 조건 비포함
```sql
SELECT *
FROM apt_list
WHERE nm LIKE '%푸르지오%'
```

## 6. 서브쿼리
```sql
SELECT *
FROM (
    SELECT dong, COUNT(*) cnt
    FROM apt_list
    GROUP BY dong
) a
WHERE cnt > 100
```
```sql
SELECT a.*, 
       CASE WHEN cnt<200 THEN '200미만 거래지역'
       ELSE '200이상 거래지역'
       END
FROM (
    SELECT dong, COUNT(*) cnt
    FROM apt_list
    GROUP BY dong
) a
```
## 7. JOIN
하나의 쿼리에 여러 테이블 엮기
```sql
SELECT a.dong, a.nm, a.size, a.price,
       b.gu, b.dong
FROM apt_list a, area_cd b
WHERE a.area_cd=b.area_cd
```
- 이너조인
- 양쪽 테이블에 조인키 기준 모두 존재하는 데이터만 나옴
- 둘 중 하나에만 있는 데이터는 나오지 않음

## 8. OUTER JOIN
```sql
SELECT a.gu, a.dong, 
    b.dong, b.nm, b.size, b.price,   
FROM area_cd a
LEFT OUTER JOIN apt_list b
ON a.area_cd=b.area_cd
AND b.con_year=2020
```
- area_cd 데이터는 모두 표시됨

## 9. SUM / MIN / MAX / AVG
```sql
SELECT YEAR, SUM(price), MIN(price), MAX(price), AVG(price)
FROM apt_list
GROUP BY YEAR
```

출처: [유튜브: SQL 초보자가 꼭 알아야 하는 10가지 문법](https://www.youtube.com/watch?v=ZsYnTSSuSiw)