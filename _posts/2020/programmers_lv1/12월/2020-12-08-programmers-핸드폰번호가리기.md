---
title: "[1단계] 핸드폰 번호 가리기"
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

전화번호 뒷자리 4자리를 제외한 나머지 숫자를 전부 *로 가린 문자열을 리턴.

```js
function solution(phone_number) {
    return '*'.repeat(phone_number.length-4)+phone_number.slice(-4);
}
``` 

repeat함수가 있다는 것을 잊고있었다. 다시 상기시키고 다음에 꼭 써먹어야겠다.     
그리고 slice함수의 인자에 음수가 들어갈 수 있다는 것을 알았다. slice(start,end)가 기본적으로 start 인덱스부터 end-1 인덱스까지 자르고, end가 없을 경우 끝까지 자른다. 