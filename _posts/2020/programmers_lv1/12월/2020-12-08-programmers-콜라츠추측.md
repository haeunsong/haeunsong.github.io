---
title: "[1단계] 콜라츠 추측"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories:
- 프로그래머스 1단계 
show_date: true
---

입력된 수가 짝수라면 2로 나눈다.
홀수라면 3을 곱하고 1을 더한다. 이와 같은 작업을 1일 될 때까지 반복한다. 만약 500번 반복해도 안된다면 -1을 반환한다.

```js
function solution(num) {
    var count = 0;
    while(num!==1){
        num%2===0 ? num/=2 : num=num*3+1
        count++;
        if(count>=500)return -1;
    }
    return count;
}
```
