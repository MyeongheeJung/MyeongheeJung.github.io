---
layout: post
title: "[코딩테스트 연습] 정수 제곱근 판별"
subtitle: ""
categories: code
comments: true
---

## 정수 제곱근 판별

### 문제 설명

임의의 양의 정수 n에 대해, n이 어떤 양의 정수 x의 제곱인지 아닌지 판단하려 합니다.<br>
n이 양의 정수 x의 제곱이라면 x+1의 제곱을 리턴하고, n이 양의 정수 x의 제곱이 아니라면 -1을 리턴하는 함수를 완성하세요.

<br>
<br>

### 제한 사항

- n은 1이상, 50000000000000 이하인 양의 정수입니다.

<br>

### 입출력 예

| n   | return |
| --- | ------ |
| 121 | 144    |
| 3   | -1     |

<br>

### 입출력 예 설명

입출력 예 #1<br>
121은 양의 정수 11의 제곱이므로, (11+1)를 제곱한 144를 리턴합니다.<br>

입출력 예 #2<br>
3은 양의 정수의 제곱이 아니므로, -1을 리턴합니다.

<br>

### 코드 작성

```js
function solution(n) {
  const number = Math.sqrt(n);
  return number % 1 === 0 ? (number + 1) ** 2 : -1;
}
```

<hr>
[ Math.sqrt() ]<br>
Math.sqrt() 함수는 숫자의 제곱근을 반환한다.<br>
주어진 숫자에 루트(√ )를 씌우고, 만약 숫자가 음수이면 NaN를 반환한다.
<br>

[ 제곱근이 정수인지 판별하기 ]<br>
정수를 1로 나누었을 경우 항상 나머지가 0이 되는 속성을 이용해서,<br>
제곱근이 양의 정수인지 확인한다.
