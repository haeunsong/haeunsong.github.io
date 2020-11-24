---
title: "[**1단계] 시저 암호"
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

![code]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/code.PNG){: .align-center .open-new}

## 풀이
```js
function solution(s, n) {
    var answer = '';
    var strArr = s.split('');
    var ansArr = [];

    for(var i=0;i<strArr.length;i++){
        var start = strArr[i].charCodeAt(0); // 문자 -> 아스키값
        console.log(start);
        if(65<=start && start<=90){ // 대문자이면
            ansArr[i]=start+n;
            if(ansArr[i]>90){
                ansArr[i] = ansArr[i]-26;
            }     
        }else if(97<=start && start<=122){ // 소문자이면
            ansArr[i]=start+n;
            if(ansArr[i]>122){
                ansArr[i] = ansArr[i]-26;
            }          
        }else if(start===32){ 
            ansArr[i]=32;
        }
    }
    for(var i=0;i<ansArr.length;i++){
        answer += String.fromCharCode(ansArr[i]); // 아스키값->문자
    }
    return answer;
}
```

## 다른 풀이
```js
function solution(s, n) {
    var upper = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
    var lower = "abcdefghijklmnopqrstuvwxyz";
    var answer= '';

    for(var i =0; i <s.length; i++){
        var text = s[i];
        if(text == ' ') {
            answer += ' '; 
            continue;
        }
        var textArr = upper.includes(text) ? upper : lower;
        var index = textArr.indexOf(text)+n;
        if(index >= textArr.length) index -= textArr.length;
        answer += textArr[index];
    }
    return answer;
}
```

js에서 65<=start<=90 이런식으로 하면 안된다는 것을 깨달았다...     65<=start && start<=90 이런식으로 하나씩 나눠서 해주어야한다. 다음엔 이런 부분 때문에 헤매지 말자..