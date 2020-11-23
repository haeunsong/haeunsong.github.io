---
title: "[프로그래머스 1단계] 소수 찾기"
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

![소수]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/cntPrimeNum.PNG){: .align-center .open-new}

## 풀이(에라토스테네스의 체 사용)
```js
function solution(n) {
    var answer = 0;
    var prime= [];
    prime.fill(0);
    for(var i=2;i<=n;i++)
        prime[i] = i;
    for(var i=2;i<=n;i++){
        if(prime[i]==0)continue;
        for(var j=i+i;j<=n;j+=i){ 
            prime[j]=0; // 소수의 배수를 모두 지워줌.(소수가 아님!)
        }
    }
    for(var i=2;i<=n;i++){
        if(prime[i]!=0) // 0이 아니면 소수.
            answer++;
    }
    
    return answer;
}
```
에라토스테네스의 체를 사용하여 풀었다. 처음에는 가장 일반적인 소수찾는 방법으로 했었는데 시간초과가 걸려 다시 풀었다. 