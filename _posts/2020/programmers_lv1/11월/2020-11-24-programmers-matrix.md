---
title: "[1단계] 행렬의 덧셈"
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

![matrix]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/matrix.PNG){: .align-center .open-new}

## 풀이
```js
function solution(arr1, arr2) {
    var answer = new Array(arr1.length);
    for(var i=0;i<arr2.length;i++){
        answer[i] = new Array(arr1[0].length);
    }
    for(var i=0;i<arr1.length;i++){
        for(var j=0;j<arr1[0].length;j++){
            answer[i][j] = arr1[i][j] + arr2[i][j];
        }
    }
    return answer;
}
``` 

비어있는 2차원 배열 생성하는 방법만 잘 알아두자.