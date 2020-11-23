---
title: "[프로그래머스 1단계] k번째 수"
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

![secondArr]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/secondArr.PNG){: .align-center .open-new}

## 풀이
```js
function solution(array, commands) {
    var answer = [];
    for(var i=0;i<commands.length;i++){
        var a = array.slice(commands[i][0]-1,commands[i][1]);
        a.sort(function(a,b){return a-b;});
        answer.push(a[commands[i][2]-1]);
    }
    return answer;
}
```

