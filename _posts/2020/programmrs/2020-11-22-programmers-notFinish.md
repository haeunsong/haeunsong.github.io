---
title: "[프로그래머스 1단계] 완주하지 못한 선수"
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

![notFinish]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/notFinish.PNG){: .align-center .open-new}

## 풀이
```js
function solution(participant, completion) {
    participant.sort();
    completion.sort();
    
    for(var i=0;i<participant.length;i++){
        if(participant[i]!=completion[i])return participant[i];
    }
}
```