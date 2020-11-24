---
title: "[1단계] 기본문제 모음 "
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

1. n의 약수의 총합 구하기
```js
function solution(n) {
    var answer = 0;
    for(var i=1;i<=n;i++){
        if(n%i==0)answer+=i;
    }
    return answer;
}
``` 

2. 자연수 뒤집어 배열로 만들기
ex> n = 12345 ==> return [5,4,3,2,1];
```js
function solution(n) {
    var answer = [];
    return String(n).split("").reverse().map((num)=>parseInt(num));
}
```

