---
title: "[1단계] 문자열을 정수로 바꾸기"
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

![strInt]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/strInt.PNG){: .align-center .open-new}


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
