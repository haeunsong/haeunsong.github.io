---
title: "[1단계] 기본문제 모음2"
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

## 1. 정수 내림차순으로 배치하기
: 정수 n을 매개변수로 입력받고 n의 각 자릿수를 내림차순으로 정렬한 정수 리턴.

```js
function solution(n) {
    return parseInt(String(n).split("").sort().reverse().join(""));
}
``` 

## 2. 짝수와 홀수
: 정수 num이 짝수일 경우 "Even" 반환, 홀수일 경우 "Odd" 반환. (0은 짝수로 판별)

```js
function solution(num) {
    return (num%2==0)?"Even":"Odd";
}
```

## 3. 최대공약수와 최소공배수
: 두 수 n,m의 최대공약수와 최소공배수를 순서대로 배열에 담아서 리턴.

```js
function fgcd(n,m){ return m==0 ? n : fgcd(m,n%m) };

function solution(n, m) {
    var answer = [];
    var gcd = fgcd(n,m);
    answer.push(gcd);
    answer.push((n*m) / gcd); 
    return answer;
}
``` 
두 수의 최대공약수: 두 수 n,m이 있을 때 m과 m % n의 최대공약수
두 수의 최소공배수: 두 수의 곱 / 최소공배수

## 4. 평균 구하기
: 정수를 담고있는 배열 arr의 평균값 리턴.

```js
function solution(arr) {
    var sum = 0;
    arr.forEach(n=>sum += n)
    return sum/arr.length;
}
```

- 다른 풀이
```js
function solution(arr){
    return arr.reduce((a,b)=>a+b) / arr.length;
}
``` 