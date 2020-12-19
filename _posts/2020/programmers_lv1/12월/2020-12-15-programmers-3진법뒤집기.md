---
title: "[1단계] 3진법 뒤집기"
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


## 풀이
```js
function solution(n) {
    var num = n.toString(3).split('').reverse().join('');
    return parseInt(num,3);
}
``` 
toString(), parseInt() 함수에 인자가 하나뿐이 아니라는 것을 알게되었다.       
진수를 설정할 수 있다는 것을 기억하자.

## toString() 함수
```js
var num = 15;
var a = num.toString(); // 15 
var b = num.toString(2); // 1111 
var c = num.toString(8); // 17
var d = num.toString(16); //f
```
- toString([radix])메서드는 숫자를 문자열로 반환한다. 
- 매개변수에 아무것도 들어가지 않으면 기본적으로 10진법을 사용하며, 2~36까지의 숫자를 넣을 수 있다.   

## parseInt() 함수 ==> parseInt(string,radix)
- 문자열 인자를 분석하여 특정 진수의 정수를 반환한다.
- 만약 string(첫번째 인자)이 문자열이 아니면 문자열로 변환한다.
- radix ==> string이 표현하는 정수를 나타내는 2~36사이의 진수. __기본값이 10이 아니다!__
- NaN을 반환하는 경우: radix가 2보다 작거나 36보다 큰 경우, 첫번째 non-whitespace 문자가 숫자로 변환되지 않는 경우.

ex> 
``` js
var hex = "7c";
var bin = parseInt(hex,16).toString(2); // hex를 10진수로 바꿨다가 2진수로 바꾼다.
``` 
```js
var bin = "1101";
var dec = parseInt(bin,2); // 2진수를 10진수로 바꾼다. 
``` 






