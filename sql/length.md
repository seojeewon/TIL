# 문자열 길이
키워드: `#LENGTH`, `#CHAR_LENGTH`
## LENGTH
문자열의 길이를 출력하는 함수
| NAME      | NAME_KOREAN |
|-----------|-------------|
| CHEOL SU  | 철수          |
| JEONG HUN | 정훈          |
```sql
SELECT LENGTH(name), LENGTH(name_korean)
FROM table
```
이렇게 하면 결과가 다음과 같다.
| LENGTH(name)      | LENGTH(name_korean) |
|-----------|-------------|
| 8  | 6          |
| 9 | 6          |

철수/정훈이 2가 아니라 6이 출력된 이유는 </br>
LENGTH함수가 byte길이를 가져오기 때문이다
- 영문자: 1byte, 한글: 3byte
 
## CHAR_LENGTH
따라서 byte 수를 계산하지 않고, 몇 개의 문자가 있는지 가져올 때 사용하는 함수가 `CHAR_LENGTH`
```sql
SELECT CHAR_LENGTH(name), CHAR_LENGTH(name_korean)
FROM table
```
| CHAR_LENGTH(name)      | CHAR_LENGTH(name_korean) |
|-----------|-------------|
| 8  | 2          |
| 9 | 2          |


참고 </br>
[[1] SQL 문자열 길이 출력 함수](https://lcs1245.tistory.com/entry/SQL-%EB%AC%B8%EC%9E%90%EC%97%B4-%EA%B8%B8%EC%9D%B4-%EC%B6%9C%EB%A0%A5-%ED%95%A8%EC%88%98-LENGTH-CHARLENGTH-LEN-DATALENGTH-LENGTHB)