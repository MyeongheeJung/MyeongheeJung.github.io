---
layout: post
title: "[코딩테스트 연습] 음양 더하기"
subtitle: ""
categories: code
comments: true
---

## 음양 더하기

### 문제 설명

어떤 정수들이 있습니다. 이 정수들의 절댓값을 차례대로 담은 정수 배열 absolutes와 이 정수들의 부호를 차례대로 담은 불리언 배열 signs가 매개변수로 주어집니다. 실제 정수들의 합을 구하여 return 하도록 solution 함수를 완성해주세요.

<br>

### 제한 사항

- absolutes의 길이는 1 이상 1,000 이하입니다.
  - absolutes의 모든 수는 각각 1 이상 1,000 이하입니다.
- signs의 길이는 absolutes의 길이와 같습니다.
  - signs[i] 가 참이면 absolutes[i] 의 실제 정수가 양수임을, 그렇지 않으면 음수임을 의미합니다.

<br>

### 입출력 예

| absolutes | signs              | result |
| --------- | ------------------ | ------ |
| [4,7,12]  | [true,false,true]  | 9      |
| [1,2,3]   | [false,false,true] | 0      |

<br>

### 입출력 예 설명

입출력 예 #1<br>

- signs가 [true,false,true] 이므로, 실제 수들의 값은 각각 4, -7, 12입니다.
- 따라서 세 수의 합인 9를 return 해야 합니다.
  <br>

입출력 예 #2<br>

- signs가 [false,false,true] 이므로, 실제 수들의 값은 각각 -1, -2, 3입니다.
- 따라서 세 수의 합인 0을 return 해야 합니다.

<br>

### 코드 작성

```js
function solution(absolutes, signs) {
  const operator = signs.map((el) => (el === true ? 1 : -1));
  const answer = absolutes.reduce((acc, cur, i) => cur * operator[i] + acc, 0);
  return answer;
}
```

<hr>
[ arr.map() ]<br>
map() 메서드는 배열 내의 모든 요소 각각에 대하여 주어진 함수를 호출한 결과를 모아 새로운 배열을 반환한다.

<br>
[ arr.reduce() ]<br>
reduce() 메서드는 배열의 각 요소에 대해 주어진 리듀서 (reducer) 함수를 실행하고, 하나의 결과값을 반환한다.<br>
> arr.reduce(callback[acc, cur, idx, arr], initialValue) 리듀서 함수는 네 개의 인자를 가집니다.
> 1. 누산기 (accumulator) : 누산기는 콜백의 반환값을 누적한다. 콜백의 첫 번째 호출이면서 initialValue를 제공한 경우에는 initialValue의 값이다.
> 2. 현재 값 (currentValue) : 처리할 현재 요소.
> 3. 현재 인덱스 (currentIndex, Optional) : 처리할 현재 요소의 인덱스. initialValue를 제공한 경우 0, 아니면 1부터 시작한다.
> 4. 원본 배열 (array, Optional) : reduce()를 호출한 배열.
> *** initialValue(Optional) : 최초 호출에서 첫 번째 인수에 제공하는 값. 초기값을 제공하지 않으면 배열의 첫 번째 요소를 사용한다. 빈 배열에서 초기값 없이 reduce()를 호출하면 오류가 발생한다.
> 리듀서 함수의 반환 값은 누산기에 할당되고, 누산기는 순회 중 유지되므로 결국 최종 결과는 하나의 값이 된다.
