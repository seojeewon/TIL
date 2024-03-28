# [프로그래머스] 숫자 게임
키워드: `#정렬`, [`#투 포인터`](../two_pointer.md)

[문제 링크](https://school.programmers.co.kr/learn/courses/30/lessons/12987)

## 해결 과정
B팀이 최대 승점을 얻기 위해서는 A팀의 idx번째 사람보다는 크면서 가장 낮은 점수인 팀원을 내보내야 한다.
1. A팀 정렬
2. B팀 정렬
```c++
int en=0;   //A팀 index
for(int st=0; st<n; st++){  //B팀 index
    if(B[st]>A[en]){
        en++;
        answer++;
    }
}
```