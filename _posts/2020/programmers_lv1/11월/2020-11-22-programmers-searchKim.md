---
title: "[1단계] 서울에서 김서방 찾기"
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

![searchKim]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/searchKim.PNG){: .align-center .open-new}

## 풀이
```js
function solution(seoul) {
    var idx = seoul.indexOf('Kim');
    return (`김서방은 ${idx}에 있다`);
}
```