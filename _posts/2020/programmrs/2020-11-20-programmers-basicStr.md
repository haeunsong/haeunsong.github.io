---
title: "[1단계] 문자열 다루기 기본"
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

![basicStr]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/basicStr.PNG){: .align-center .open-new}

## 풀이
```js
function solution(s) {
    var sint = parseInt(s);
    if ((s.length==4 || s.length==6)&& s==sint) return true;
    else return false;
}
```