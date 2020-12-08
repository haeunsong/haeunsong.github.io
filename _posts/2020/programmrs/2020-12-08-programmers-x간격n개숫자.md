---
title: "[**1단계] x만큼 간격이 있는 n개 숫자"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories:
- 프로그래머스
show_date: true
---

정수x와 자연수 n을 입력받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트 리턴.     
ex> x = 4, n = 3 ==> [4,8,12]

## 처음 풀이
```js
function solution(x, n) {
    var answer=[];
    var v=x;
    for(var i=0;i<n;i++){
        answer.push(v);
        v+=x;
    }
    return answer;
}
```

## 다른 풀이(map함수 이용!)
```js
function solution(x, n) {
    var answer=[];
    answer = Array(n).fill(x).map((v,i)=>v*(i+1))
    return answer;
}
``` 

map 함수, Array(), fill() 함수 까먹지 말자.    
Array(n)으로 n 크기의 배열을 만들어주고 fill(x)로 모든 배열의 원소를 x로 채워준다.      

## array.map(callbackFunction(currenValue, index, array), thisArg)        
- currentValue: 배열 내 현재 값
- index: 배열 내 현재 값의 인덱스. 하나씩 증가한다.
- array: 현재 배열
- thisArg: callbackFunction 내에서 this로 사용될 값.

4 = 4 * (0+1)     
8 = 4 * (1+1)     
12 = 4 * (2+1)     
===> 구하려는 값 = 현재값 * (현재 인덱스 + 1)

