# Tips
### 💡cout 소수점 표시
```c++
cout << fixed;
cout.precision(3);
cout << x;
``` 

### 💡너무 큰 배열을 정렬해야 할 때
배열의 크기가 너무 크면(ex. 천만) 메모리가 초과나, 정렬할 때 시간초과가 날 수 있다.
- 따라서 이럴 때는 [`우선순위 큐`](priority_queue.md)를 고려해보자