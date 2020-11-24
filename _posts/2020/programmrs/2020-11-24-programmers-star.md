---
title: "[1단계] 직사각형 별찍기"
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

n = [가로길이, 세로길이]

## 풀이
```js
process.stdin.setEncoding('utf8');
process.stdin.on('data', data => {
    const n = data.split(" ");
    const a = Number(n[0]), b = Number(n[1]);
    for(var i=0;i<b;i++){
        for(var j=0;j<a;j++){
            process.stdout.write('*');
        }
        process.stdout.write('\n');
    }
    
});
```

## 다른 풀이
```js
process.stdin.setEncoding('utf8');
process.stdin.on('data', data => {
    const n = data.split(" ");
    const a = Number(n[0]), b = Number(n[1]);
    const row = '*'.repeat(a)
    for(let i =0; i < b; i++){
        console.log(row)
    }
});
```
repeat 함수도 있다는 것을 알았다. 다음에 이용해보자.