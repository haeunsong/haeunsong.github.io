---
title: "[1단계] 문자열 내 p와 y의 개수"
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

![countpy]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/countpy.PNG){: .align-center .open-new}

## 풀이
```js
function solution(s){
    var lowStr = s.toLowerCase();
    var pcount=0; var ycount=0; 
    for(var i=0;i<lowStr.length;i++){
        if(lowStr[i]==='p')pcount++;
        else if(lowStr[i]==='y')ycount++;
    }
    if(pcount===ycount)return true;
    else return false;
}
``` 
# 다른 풀이(split() 사용)
```js
function solution(s){
    return s.toUpperCase().split("P").length === s.toUpperCase().split("Y").length;
}
```
