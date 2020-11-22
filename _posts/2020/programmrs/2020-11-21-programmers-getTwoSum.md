---
title: "[프로그래머스] 두 개 뽑아서 더하기"
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

![getTwoSum]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/getTwoSum.PNG){: .align-center .open-new}

## 풀이
```js
function solution(numbers) {
    var answer = [];
    var ans;
    for(var i=0;i<numbers.length;i++){
        for(var j=i+1;j<numbers.length;j++){
            ans = numbers[i]+numbers[j];
            if(!answer.includes(ans)){
                answer.push(ans)
            }
        }
    }
    answer.sort(function(a,b){
        return a-b;
    });
    return answer;
}
``` 
마지막에 오름차순 정렬시 그냥 answer.sort()로 하게되면 문자열을 기준으로 정렬되므로(1,12,3,4...) 숫자 기준 정렬을 위해 꼭 function(a,b){return a-b;}를 넣어주어야한다.

## 다른 풀이(Set 사용)
```js
function solution(numbers) {
    var answer = [];
    var tmp = [];
    var ans;
    for(var i=0;i<numbers.length;i++){
        for(var j=i+1;j<numbers.length;j++){
            ans = numbers[i]+numbers[j];
            tmp.push(ans);
        }
    }
    answer = Array.from(new Set(tmp));
    answer.sort(function(a,b){
        return a-b;
    });
    return answer;
}
``` 
집합 Set은 unique 값만 저장할 수 있기 때문에 배열에 넣으면 중복이 제거된다.