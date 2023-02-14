---
layout: post
title: "[코딩테스트 연습] 나머지가 1이 되는 수 찾기"
subtitle: ""
categories: code
comments: true
---

## 나머지가 1이 되는 수 찾기

### 문제 설명

자연수 n이 매개변수로 주어집니다. n을 x로 나눈 나머지가 1이 되도록 하는<br> 가장 작은 자연수 x를 return 하도록 solution 함수를 완성해주세요.<br> 답이 항상 존재함은 증명될 수 있습니다.

<br>
<br>

### 제한 사항

- 3 ≤ n ≤ 1,000,000

<br>

### 입출력 예

| n   | result |
| --- | ------ |
| 10  | 3      |
| 12  | 11     |

<br>

### 입출력 예 설명

입출력 예 #1<br>
10을 3으로 나눈 나머지가 1이고, 3보다 작은 자연수 중에서 문제의 조건을<br> 만족하는 수가 없으므로, 3을 return 해야 합니다.<br>

입출력 예 #2<br>
12를 11로 나눈 나머지가 1이고, 11보다 작은 자연수 중에서 문제의 조건을<br> 만족하는 수가 없으므로, 11을 return 해야 합니다.

<br>

### 코드 작성

```js
function solution(n) {
  let result = 0;
  for (let i = 1; i <= n; i++) {
    if (n % i === 1) {
      result = i;
      break;
    }
  }
  return result;
}
```

<hr>
[ TIP ]<br>
나머지 연산자를(%) 활용하여 나머지가 1이 되는 가장 작은 자연수를 구하고,<br> break를 사용하여 반복문을 종료시킨다.
<br>
