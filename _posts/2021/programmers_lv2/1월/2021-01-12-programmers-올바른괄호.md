---
title: "[2단계] 올바른 괄호"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories:
- 프로그래머스 2단계
show_date: true
---

괄호가 바르게 짝지어지면 true, 그렇지 않으면 false를 반환한다.    
'(' 문자로 열렸으면 반드시 ')' 문자로 닫혀야한다.         
ex> "(())()" => true        
    ")()(" => false      

## 풀이
```js
function solution(s){
    var tmp = [];
    var flag = false;
    if(s[0]==")"){
        tmp.push(s[0]);
        flag = true;
    }
    for(var i=0;i<s.length;i++){
        if(s[i]=='(' && flag==false)tmp.push(s[i]);
        else if(s[i]==')' && flag==false)tmp.pop(s[i]);
    }
    if(tmp.length===0) return true;
    else return false;
}
```

1. 만약 첫 문자가 ")" 일 경우 일단 tmp에 넣는다. 이 경우인지 아닌지를 확인하기 위해 flag 변수를 만들었다. 
2. '(' && 첫 문자가 ')'가 아니라면 =>  tmp에 넣기
3. ')' && 첫 문자가 ')'가 아니라면 => tmp에서 뺴기
4. 이런식으로 tmp에 넣고 빼고 과정을 반복하는데 마지막에 tmp 배열의 길이가 0이 아니라면 괄호의 짝이 맞지 않는다는 뜻이다. 

