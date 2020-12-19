---
title: "[1단계] 예산"
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

부서별로 신청한 금액이 들어있는 배열 d와 예산 budget이 매개변수로 주어질 때, 최대 몇 개의 부서에 물품을 지원할 수 있는지 return.<br><br>   

ex> d = [1,3,2,4,5] , budget = 9 , result ==> 3


우선 d 배열을 오름차순으로 정렬하고, 배열의 첫 원소부터 더한 값이 예산을 넘어가지 않을 때까지 계속 더한다. 더한 값이 예산을 넘어가게 되면 그 때의 count값을 반환한다.

## 풀이
```js
function solution(d, budget) {
    var sum=0,count=0;
    d.sort((a,b)=>a-b).forEach((v)=>{
        sum += v;
        if(sum<=budget)count++;
    })
    return count;
}
```