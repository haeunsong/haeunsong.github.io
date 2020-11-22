---
title: "[프로그래머스] 체육복"
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

![clothes]({{ site.url }}{{ site.baseurl }}./assets/images/post/programmers/clothes.PNG){: .align-center .open-new}

## 풀이
```js
function solution(n, lost, reserve) {
    var answer = 0;
    var nums=[];
    for(var i=0;i<=n;i++)nums.push(1); // 일단 모두가 하나씩 가지고 있다.
    for(var i=1;i<=n;i++){
        for(var j=0;j<lost.length;j++){ // lost에 적힌 번호를 인덱스로 가진 원소를 0으로 바꿔준다.
            if(i==lost[j]) nums[i]=0;
        }
        for(var j=0;j<reserve.length;j++){ // 여벌을 더 가지고 있으므로(reserve 배열) 해당 번호 원소를 2로 바꿔준다.(한 개 추가)
            if(i==reserve[j]) nums[i]++;
        }
    }
    for(var i=1;i<=n;i++){
        if(nums[i]===0 && nums[i-1]===2){ // 체육복이 없는 사람의 앞뒤를 확인해서 체육복을 빌린다.
            nums[i-1]--; nums[i]++;
        }else if(nums[i]===0 && nums[i+1]===2){
            nums[i+1]--; nums[i]++;
        }
    }
    for(var i=1;i<=n;i++){
        if(nums[i]>0)answer++;
    }
    return answer;
}
```