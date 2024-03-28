# 문자열 자르기
키워드: `#SUBSTRING`, `#LEFT` `#RIGHT`

## SUBSTRING
```SQL
SUBSTRING(문자열, 시작위치, 길이)
```

```SQL
SELECT SUBSTRING('WWW.GOOGLE.COM', 3, 5)
//W.GOO
```
- 1-indexed

## LEFT
왼쪽부터 잘라서 반환
```SQL
LEFT(문자열, 길이)
```

## RIGHT
오른쪽부터 잘라서 반환
```SQL
RIGHT(문자열, 길이)
```

### 관련 문제
- [[HR]Higher Than 75 Marks](https://www.hackerrank.com/challenges/more-than-75-marks/problem?isFullScreen=true)