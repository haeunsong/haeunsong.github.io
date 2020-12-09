---
title: "[1단계] 하샤드 수"
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

양의 정수 x가 하샤드 수이려면 x의 자릿수의 합으로 나누어져야한다.      
ex> 18의 자릿수 합 = 1 + 8 = 9, 18은 9로 나누어떨어지므로 18은 하샤드 수이다.      
하샤드 수인지 아닌지 boolean 값 리턴하기.


```js
function solution(x) {
    var str = String(x); var sum = 0;
    for(var i=0;i<str.length;i++)
        sum += parseInt(str[i]);
    if(x%sum==0)return true;
    else return false;
}
```