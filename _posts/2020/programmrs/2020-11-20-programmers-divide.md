---
title: "[프로그래머스 1단계] 나누어 떨어지는 숫자 배열"
show_date: true
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories:
- 프로그래머스
# description: 
# article_tag1: 
# article_section: 
# meta_keywords: 
# last_modified_at: 
# toc: true
# toc_sticky: true
# toc_label: 목차
--- 

![divide]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/divide.PNG){: .align-center .open-new}

## 풀이
```js
function solution(arr, divisor) {
    var answer = [];
    for(var i=0;i<arr.length;i++){
        if(arr[i]%divisor==0){
            answer.push(arr[i]);    
        }
        answer.sort(function(a,b){
            return a-b;
        });
    }
    if(answer.length===0)answer.push(-1);
    return answer;
}
```