---
title: "[2단계] 기능 개발"
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

각 기능은 진도가 100%일 때 서비스에 반영할 수 있다. 각 기능의 개발속도는 모두 달라서 뒤에 있는 기능이 앞에 있는 기능보다 먼저 개발될 수 있고, 이때 뒤에 있는 기능은 앞에 있는 기능이 배포될 때 함께 배포된다.       
progresses => 먼저 배포되어야하는 순서대로 작업의 진도가 적힌 정수 배열          
sppeds => 각 작업의 개발 속도가 적힌 정수 배열      

ex1> progresses = [93,30,55] / speeds = [1,3,5] / return = [2,1]        
7일째에 두 개의 기능, 9일째에 1개의 기능 배포 가능
<br>
ex2> progresses = [95,90,99,99,80,99] / speeds = [1,1,1,1,1,1] / return = [1,3,2]       
각각 작업이 끝나기까지 남은 일 수는 5,10,1,1,20,1일이다. 즉, 5일째에 1개의 기능, 10일째에 3개의 기능, 20일째에 2개의 기능 배포 가능. 


## 풀이
```js
function solution(prg, spd) {
    let tmp = [];
    let answer = [];
    let flag, count=1;
    for(let i=0;i<prg.length;i++){
        tmp.push(Math.ceil((100-prg[i])/spd[i]));
    }
    flag = tmp[0];
    for(let j=1;j<tmp.length;j++){
        if(flag<tmp[j]){
            answer.push(count);
            flag = tmp[j];
            count = 1;
        }else count++;        
        if(j===tmp.length-1)answer.push(count);
    }
    return answer;
}
```

두번째 예시를 예로 들면 tmp = 5,10,1,1,20,1가 된다. tmp 배열의 길이만큼 차례대로 기준이 되는 flag보다 다음 수가 작으면 그대로 answer배열에 갯수를 넣어주고 flag를 재설정, count=1로 초기화해준다. 그렇지않으면 count 개수를 늘려간다. 마지막으로 검사를 마쳤을 때 count 개수를 꼭 tmp에 넣어주어야한다. _처음에 이 부분을 하지 않았다._