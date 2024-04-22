# JWT
키워드: `#stateless`, `#header`, `#payload`, `#signature`, `#access token`, `#refresh token`
### 정의
`Json Web Token`의 준말. 사용자의 정보를 저장한 웹토큰.

## 장점
- 세션과 달리 서버에 저장하지 않아도 된다.
- `stateless`환경에서 사용자 정보를 주고 받을 수 있다.

## 단점
- `Claim`이 많거나 클 경우 토큰의 크기가 커져서 네트워크에 부하
- 탈취되었을 때 정보 유출 가능

## 구성
`3가지` 파트로 나뉘며, 점으로 구분됨
### Header
- 서명시 사용하는 `키`

- 토큰 `유형`

- 서명 `암호화 알고리즘`

### Payload
정보의 조각인 `Claim`이 담김

- `Claim`: key-value

### Signature
`Header`와 `Payload`를 이용해 서명이 생성됨.(헤더에서 정의한 알고리즘에 의해)
- 토큰 `검증`에 사용됨

## Access Token & Refresh Token
> JWT는 탈취되었을 때 서버는 그 사실을 알 수 없다. 따라서 `유효기간`이 필요

`유효기간`이 다른 토큰 두 가지

### Access Token
- 유효기간이 `짧다`
- 평소 API 통신시 사용

### Refresh Token
- 유효기간이 `길다`
- `Access Token`이 만료되었을 때, 이를 `갱신`하기 위한 용도로 사용

### 과정
1. 로그인에 성공한 클라이언트는 `refresh token`과 `access token`을 서버로부터 받음
   
2. `refresh token`과 `access token`을 저장

3. 클라이언트는 헤더에 `access token`을 넣고 API 통신

4. `access token` 만료
   1. 서버는 `401(unauthorized)`에러 응답
   2. 클라이언트가 만료됨을 앎
   3. 클라이언트가 `Refresh Token`넣고 재요청
   4. `Refresh Token`을 받은 서버는 응답 헤더에 새로운 `Access Token` 넣어 응답
   5. 만약 `Refresh Token`도 만료되었다면 재로그인

