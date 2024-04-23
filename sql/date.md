# 날짜 차이
키워드: `#DATEDIFF`, `#TIMESTAMPDIFF`
## DATEDIFF
간단하게 `일(day)`차이를 구하고 싶을 때
```sql
SELECT DATEDIFF('2024-04-23', '2024-02-05')
FROM DUAL;
```
```SQL
DATEDIFF(날짜1, 날짜2)
```
기본적으로 날짜1-날짜2

## TIMESTAMPDIFF
`연`, `월`, `시간`, `초` 등을 지정하여 구하고 싶을 때
```SQL
SELECT TIMESTAMPDIFF(SECOND, '2022-08-26 15:30:33', '2022-08-26 15:32:21') FROM DUAL;
/*	초 차이: 108    */
```
- `SECOND`: 초
- `MINUTE`: 분
- `HOUR`: 시간
- `DAY`: 일
- `WEEK`: 주
- `MONTH`: 월
- `QUARTER`: 분기
- `YEAR`: 년