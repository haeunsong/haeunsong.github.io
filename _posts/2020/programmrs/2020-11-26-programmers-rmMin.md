---
title: "[1단계] 제일 작은 수 제거하기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories:
- 프로그래머스
show_date: true
---

정수를 저장한 배열 arr에서 가장 작은 수를 제거한 배열 리턴.    
리턴하려는 배열이 비어있는 경우엔 배열에 -1을 채워 리턴.    
ex> arr = [4,3,2,1] ==> return [4,3,2]
    arr = [10] ==> return [-1]

```js
function solution(arr) {
    var answer = [];
    var min = Math.min.apply(null,arr);
    answer = arr.filter(n=>n!==min);
    if(answer.length===0)answer.push(-1);
    return answer;
}
```

Math.min() 함수 사용시 Math.min(arr) 이런식으로 인자에 바로 숫자 배열을 넣지 못한다.    
그래서 Math.min.apply(null,arr); 을 이용하여 최솟값을 구한다.     
arr에 최솟값이 여러개인 경우가 있기 때문에 indexOf함수를 사용하기보다 최솟값을 찾아준 후 filter함수를 이용해서 최솟값을 제거해준 배열을 리턴하였다. 