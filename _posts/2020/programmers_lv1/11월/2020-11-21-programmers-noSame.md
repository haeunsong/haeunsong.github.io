---
title: "[1단계] 같은 숫자는 싫어"
show_date: true
# layout: single
# author_profile: true
# read_time: true
# comments: true
# share: true
# related: true
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

![noSame]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/noSame.PNG){: .align-center .open-new}

**- 처음에는 include함수를 써서 하나씩 확인하는 방법으로 했는데 시간초과 걸림..<br>

## 풀이
```js
function solution(arr)
{
    var answer = [];
    var cur = arr[0];
    answer.push(cur);
    for(var i=1;i<arr.length;i++){
        if(cur!=arr[i]){
            answer.push(arr[i])
            cur=arr[i];
        }
    }   
    return answer;
}
```
