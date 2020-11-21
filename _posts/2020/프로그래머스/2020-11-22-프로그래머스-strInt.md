---
title: [프로그래머스] 문자열을 정수로 바꾸기
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories:
- 프로그래머스
last_modified_at:
---

## 처음 작성 코드
```js
function solution(s) {
    var answer = 0;
    if (s.charAt(0)==='+'){
        s = s.slice(1,s.length)
        answer = parseInt(s)
    }else if (s.charAt(0)==='-'){
        s=s.slice(1,s.length)
        answer = parseInt(s) * -1
    }else{
        answer=parseInt(s)
    }
    return answer;
}
```

## 이후 작성 코드
```js
function solution(s) {
    var answer = 0;
    answer = s*1  
    return answer;
}
```
