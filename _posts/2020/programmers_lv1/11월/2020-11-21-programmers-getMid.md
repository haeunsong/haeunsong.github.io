---
title: "[1단계] 가운데 글자 가져오기"
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

![가운데 글자 가져오기]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/getMid.PNG){: .align-center .open-new}


# 풀이
```js
function solution(s) {
    return (s.length%2==0)?s.substr(s.length/2-1,2):s.substr(s.length/2,1)
}
```
### substr(start,length): 문자열에서 특정 부분만 골라내고 싶을 때 사용한다.
ex> 
var s = '123456';
s.substr(1,4); // '2345'
### 만약 length값이 없다면 문자열 끝까지 가져온다.
