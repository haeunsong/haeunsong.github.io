---
title: "[**1단계] 이상한 문자 만들기"
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

각 단어의 짝수번째 알파벳은 대문자로, 홀수번째 알파벳은 소문자로 바꾼 문자열 리턴.        
ex> s = "try hello world"       
    return "TrY HeLlO WoRlD"     

```js
function solution(s) {
    var arr = s.split(' ');
    var tmp = '';
    
    arr.map((word,idx)=>{
        for(var i=0;i<word.length;i++){
            i%2==0 ? tmp += word[i].toUpperCase() : tmp += word[i].toLowerCase();
        }
        if(idx+1!==arr.length) tmp += ' ';
    })
    return tmp;
}
``` 

## 주의할 점

1. 코드를 짧게 하려고 arr변수를 사용하지 않고 s.split(' ').map(...) 으로 하면 매번 split을 하여 런타임 에러가 발생한다.          
2. 마지막 tmp += ' '; 부분에 if 조건문을 달아주지 않으면 마지막에 공백이 하나 추가된 문자열이 리턴되므로 현재 단어(word)가 마지막 단어가 아닐 경우에만 공백 문자를 추가해주어야한다.  