---
title: "[**1단계] 문자열 내 마음대로 정렬하기"
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

문자열로 구성된 strings와 정수 n이 주어졌을 때, 각 문자열의 인덱스 n번째 글자를 기준으로 오름차순 정렬을 한다.      
ex1>       
strings: ["sun","bed","car"]       
n: 1      
return: ["car',"bed","sun"]         


ex2>       
strings: ["abce","abcd","cdx"]         
n: 2      
return:  ["abcd","abce","cdx"]     

__js에서는 true(1)와 false(0)를 연산할 수 있다. 즉, true-false = 1, false-true=-1 이다.__

## 풀이
```js
function solution(strings, n) {
    strings.sort(function(a,b){
        var first = a[n];
        var second = b[n];
        if(first===second){
          // 그냥 문자열 전체를 비교
            return (a>b) - (a<b);
        }else{
            return (first>second) - (first<second);
        }
    }) 
    return strings;
}
```

이 문제를 풀기위해서는 js의 sort함수 내부구조를 알고 있어야한다.       
- function(a,b) < 0 이면 a를 b보다 작은 인덱스로 정렬한다.
- function(a,b) == 0 이면 a와 b의 순서를 바꾸지 않는다.
- function(a,b) > 0 이면 a를 b보다 큰 인덱스로 정렬한다. 


## 참고
```js
arr = ["orange","mynameishahah","apple","hi"]
arr.sort(function(a,b){
  // 문자열 길이 오름차순
  return a.length - b.length;
})
// ["hi", "apple", "orange", "mynameishahah"]
``` 
위의 return 문을 a.length + b.length 로 할 경우 문자열 길이가 내림차순으로 정렬된다. 

