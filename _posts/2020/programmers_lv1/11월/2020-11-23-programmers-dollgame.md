---
title: "[1단계] 크레인 인형뽑기"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: false
categories:
- 프로그래머스 1단계
show_date: true
---

## 풀이
```js
function solution(board, moves) {
    var result=0;
    var tmp=[]; // 바구니
    
    moves.forEach(move=>{
        var start=0;
        while(true){
            if(board[start][move-1]!==0){
                // 바구니에 담긴 마지막 인형과 board의 선택된 인형이 일치할 경우 인형 삭제
                if(tmp.length!==0 && tmp[tmp.length-1]===board[start][move-1]){
                    tmp.pop();
                    result += 2;
                }else{
                    tmp.push(board[start][move-1]);
                }
                board[start][move-1]=0;
                break;
            }
            start++;
            if(start===board.length)break;          
        }
    })
    return result;
}
```
처음에는 이중 for문을 사용하다가 'Cannot read property '0' of undefined' 오류가 계속 떴다. 그래서 다른 풀이를 찾아보다가 forEach문을 사용하기로 했다. 마지막 if(start===board.length)break; 이 구문이 꼭 있어야한다. forEach문 사용이 익숙하지 않은데 익숙하게 만들어야겠다. 다음에 또 풀어보자.