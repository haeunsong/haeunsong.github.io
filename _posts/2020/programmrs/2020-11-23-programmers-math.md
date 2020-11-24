---
title: "[1단계] 모의고사"
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

![math]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/math.PNG){: .align-center .open-new}

## 풀이
```js
function solution(answers) {
    var answer = [];
    var count = [0,0,0];
    var one=[1,2,3,4,5];
    var two=[2,1,2,3,2,4,2,5];
    var three=[3,3,1,1,2,2,4,4,5,5];

    for(var i=0;i<answers.length;i++){
        if(one[i%one.length]===answers[i])count[0]++;
        if(two[i%two.length]===answers[i])count[1]++;
        if(three[i%three.length]===answers[i])count[2]++;
    }
    var max = Math.max.apply(null,count);
    for(var i=0;i<count.length;i++){
        if(max===count[i])answer.push(i+1)
    }
    return answer;
}
```
배열에서 가장 큰 값을 반환하고 싶을 떄는 Math.max.apply()함수를 사용하면 된다.                                                                                      