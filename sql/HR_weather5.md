# [HR] Weather Observation Station 5
[링크](https://www.hackerrank.com/challenges/weather-observation-station-5/problem?isFullScreen=true)

## 문제
가장 짧은 이름을 가진 도시, 가장 긴 이름을 가진 도시를 구하여라.

단, 가장 짧은/긴 도시가 2개 이상이라면, 알파벳 순으로 먼저 오는 것을 골라라

| Field  | Type        |
|--------|-------------|
| ID     | NUMBER      |
| CITY   | VARCHAR(21) |
| STATE  | VARCHAR(2)  |
| LAT_N  | NUMBER      |
| LONG_W | NUMBER      |

### Sample Output
```
ABC 3
PQRS 4
```

## 해결 과정

1. 컬럼은 도시 이름이랑, 이름 길이
   ```sql
   SELECT CITY, LENGTH(CITY)
   FROM CITY
   ```
2. 근데 이름 긴 순으로 정렬
   ```sql
   SELECT CITY, LENGTH(CITY) l
   FROM CITY
   ORDER BY l DESC
   ```
3. 길이가 같은 도시 여러 개일 경우 알파벳 순
   ```sql
   SELECT CITY, LENGTH(CITY) l
   FROM CITY
   ORDER BY l DESC, CITY
   ```
4. 이름이 가장 긴 도시 1개만 
   ```sql
   SELECT CITY, LENGTH(CITY) l
   FROM CITY
   ORDER BY l DESC, CITY
   LIMIT 1
   ```
5. 길이가 가장 짧은 도시 찾는 과정 같음 - 답 나옴
   ```sql
   SELECT CITY, LENGTH(CITY) l
   FROM CITY
   ORDER BY l DESC, CITY
   LIMIT 1;

   SELECT CITY, LENGTH(CITY) l
   FROM CITY
   ORDER BY l , CITY
   LIMIT 1;
   ```