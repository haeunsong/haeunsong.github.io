---
title: "[**2단계] 프린터"
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

중요도가 높은 문서를 먼저 인쇄한다.<br>
1. 인쇄 대기목록의 가장 앞에 있는 문서(J)를 대기목록에서 꺼냅니다. 
2. 나머지 인쇄 대기목록에서 J보다 중요도가 높은 문서가 한 개라도 존재하면 J를 대기목록의 가장 마지막에 넣습니다.
3. 그렇지 않으면 J를 인쇄합니다.

>> 현재 대기목록에 있는 문서의 중요도가 순서대로 담긴 배열 priorities와 내가 인쇄를 요청한 문서가 현재 대기목록의 어떤 위치에 있는지를 알려주는 location이 매개변수로 주어질 때, 내가 인쇄를 요청한 문서가 몇 번째로 인쇄되는지 return 하도록 solution 함수를 작성해주세요.

ex>   
priorites: [2,1,3,2] / location: 2 / return: 1 <br>
priorites: [1,1,9,1,1,1] / location: 0 / return: 5 <br>

## 풀이

```js
function solution(priorities, location) {
    var userIndex = location;
    var answer = 1;
    while(priorities.length>0){
        // 가장 앞에 있는 문서 추출
        var first = priorities.shift();
        // 처음것보다 중요도가 더 높은 것이 있다면 처음것 뒤로보내기
        if(priorities.some(val=>val>first)){
            priorities.push(first);
        }
        // 처음것이 가장 중요도가 높을때
        else{
            if(userIndex==0)break;
            else answer++;
        }
        if (userIndex === 0) userIndex = priorities.length - 1;
        else userIndex --;
    }
    return answer;
}
``` 

some() 메서드는 배열 안의 요소 중 하나라도 주어진 판별 함수를 통과하면 true를 반환한다.<br> 
ex> [2,12,5,3].some(val => val>10); // true

이 문제 다시 풀어봐야겠다...
