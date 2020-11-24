---
title: "[1단계] 기본문제 모음 "
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

## 1. n의 약수의 총합 구하기

```js
function solution(n) {
    var answer = 0;
    for(var i=1;i<=n;i++){
        if(n%i==0)answer+=i;
    }
    return answer;
}
``` 
---------------------------------------------

## 2. 자연수 뒤집어 배열로 만들기    
: n = 12345 ==> return [5,4,3,2,1];

```js
function solution(n) {
    var answer = [];
    return String(n).split("").reverse().map((num)=>parseInt(num));
}
```

---------------------------------------------

## 3. 정수 제곱근 판별
: 양의 정수 n이, 어떤 양의 정수x의 제곱이면 x+1의 제곱을 리턴하고, 그렇지 않으면 -1을 리턴한다.

```js
function solution(n) {
    if(Number.isInteger(Math.sqrt(n))) return Math.pow((Math.sqrt(n)+1),2);
    else return -1;
}
``` 
정수를 판별하고 싶을때 **Number.isInteger(값)** 함수를 사용할 수 있다는 것을 기억하자. 

---------------------------------------------

## 4. 자릿수 더하기
: 자연수 n의 각 자릿수 합을 구해서 리턴한다.

```js
// 방법 1 (다른 언어에세도 사용하는 정석적인 방법)
function solution(n){
    var answer = 0;
    while(n!=0){
        var r = n%10;
        n=parseInt(n/10);
        answer += r;
    }
}

// 방법 2 (js특유의 형변환 덕분에 가능한 방법)
function solution(n){
    return String(n).split("").reduce((a,b)=>(a*1)+(b*1));
}
``` 

방법 2에서 문자열에 1을 곱해주면 자동으로 **정수**로 변한다.
reduce함수를 처음 써보았는데 다음에도 필요할때마다 사용해야겠다.

---------------------------------------------

- reduce 함수 사용법

```js
const array1 = [1, 2, 3, 4];
const reducer = (accumulator, currentValue) => accumulator + currentValue;

// 1 + 2 + 3 + 4
console.log(array1.reduce(reducer));

// 5 + 1 + 2 + 3 + 4
console.log(array1.reduce(reducer, 5));
```