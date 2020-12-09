---
title: "[1단계] 수박수박 문제"
show_date: true
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories:
- 프로그래머스 1단계
# description: 
# article_tag1: 
# article_section: 
# meta_keywords: 
# last_modified_at: 
# toc: true
# toc_sticky: true
# toc_label: 목차
--- 

![수박수박]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/수박.PNG){: .align-center .open-new}


## 풀이
```js
function solution(n) {
    var answer = '';
    for(var i=1;i<=n;i++){
        if(i%2==0){
            answer+='박'
        }else{
            answer+='수'
        }
    }
    return answer;
}
```
