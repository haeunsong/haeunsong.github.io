---
title: "[1단계] 두 정수 사이의 합"
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

![getSum]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/getSum.PNG){: .align-center .open-new}


<!-- ![getSum](./image/getSum.PNG) -->
## 처음 내 코드
```js
function solution(a, b) {
    var answer = 0;
    for(var i=Math.min(a,b);i<=Math.max(a,b);i++){
        answer += i;
    }
    return answer;
}
```
## 다른 사람의 코드
*가우스 공식 사용
```js
function solution(a, b) {
    return (Math.abs(a-b)+1)*(a+b)/2;
}
```
