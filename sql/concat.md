# 문자열 합치기
키워드: `#CONCAT`, `#+`

## CONCAT
문자열을 합칠 때는 되도록이면 CONCAT을 사용한다.
```SQL
SELECT CONCAT('SQL', 'SERVER')
//SQLSERVER
```

## + 더하기 연산자
```SQL
SELECT 'SQL' + 'Server' + '2019'  
//SQLSERVER2019
```
문자열과 문자열을 합칠 때는 문제가 발생하지 않지만,

문자열과 숫자를 합칠 경우 오류가 발생할 수 있다.

## CONCAT_WS(구분자로 합치기)
문자열을 특정 구분자로 합칠 때
```SQL
SELECT CONCAT_WS(', ', 'SQL', 'Server', '2019') 
/*SQL, SERVER, 2019*/
```

### 관련 문제
[[HR] The PADS](https://www.hackerrank.com/challenges/the-pads/problem?isFullScreen=true)

참고 </BR>
[문자열 합치기](https://gent.tistory.com/437)