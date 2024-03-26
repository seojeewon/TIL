# [HR] Weather Observation Station 8
[링크](https://www.hackerrank.com/challenges/weather-observation-station-8/problem?isFullScreen=true)
## 문제
모음(a,e,i,o,u)로 시작하고 끝나는 도시 이름 나열, 중복 없이

| Field  | Type        |
|--------|-------------|
| ID     | NUMBER      |
| CITY   | VARCHAR(21) |
| STATE  | VARCHAR(2)  |
| LAT_N  | NUMBER      |
| LONG_W | NUMBER      |

## 해결 과정
(모음으로 시작하는 조건) AND (모음으로 끝나는 조건)
```SQL
SELECT CITY
FROM STATION
WHERE (CITY LIKE 'A%' OR CITY LIKE 'E%' OR CITY LIKE 'I%' OR CITY LIKE 'O%' OR CITY LIKE 'U%') 
AND 
(CITY LIKE '%A' OR CITY LIKE '%E' OR CITY LIKE '%I' OR CITY LIKE '%O' OR CITY LIKE '%U')
GROUP BY CITY;
```