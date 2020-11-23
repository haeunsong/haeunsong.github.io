---
title: "[프로그래머스 1단계] 문자열 내림차순으로 배치하기"
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

![reverse]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/reverse.PNG){: .align-center .open-new}

## 풀이
```js
function solution(s) {
    var answer = '';
    answer = s.split('').sort().reverse().join('');  
    return answer;
}
```