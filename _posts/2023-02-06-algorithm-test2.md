---
layout: post
title: "[코딩테스트 연습] x만큼 간격이 있는 n개의 숫자"
subtitle: ""
categories: code
comments: true
---

## x만큼 간격이 있는 n개의 숫자

### 문제 설명

함수 solution은 정수 x와 자연수 n을 입력 받아, x부터 시작해 x씩 증가하는 숫자를 n개 지니는 리스트를 리턴해야 합니다.<br>
다음 제한 조건을 보고, 조건을 만족하는 함수, solution을 완성해주세요.

<br>
<br>

### 제한 사항

- x는 -10000000 이상, 10000000 이하인 정수입니다.
- n은 1000 이하인 자연수입니다.

<br>

### 입출력 예

| x   | n   | answer       |
| --- | --- | ------------ |
| 2   | 5   | [2,4,6,8,10] |
| 4   | 3   | [4,8,12]     |
| -4  | 2   | [-4, -8]     |

<br>

### 코드 작성

```js
function solution(x, n) {
  const answer = [];
  for (let i = 1; i <= n; i++) {
    answer[i - 1] = x * i;
  }
  return answer;
}
```

<hr>
[ Math.sqrt() ]<br>
반복문과 배열의 index를 활용하여 n번이 될 떄까지 x씩 증가하는 숫자를 배열에 담아주었다.<br>
