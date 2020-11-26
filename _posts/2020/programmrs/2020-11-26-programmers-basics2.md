---
title: "[1단계] 기본문제 모음2"
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

## 1. 정수 내림차순으로 배치하기
: 정수 n을 매개변수로 입력받고 n의 각 자릿수를 내림차순으로 정렬한 정수 리턴.

```js
function solution(n) {
    return parseInt(String(n).split("").sort().reverse().join(""));
}
``` 