---
layout: post
title: "[코딩테스트 연습] 두 정수 사이의 합"
subtitle: ""
categories: code
comments: true
---

## 두 정수 사이의 합

### 문제 설명

두 정수 a, b가 주어졌을 때 a와 b 사이에 속한 모든 정수의 합을 리턴하는 함수, solution을 완성하세요.<br>
예를 들어 a = 3, b = 5인 경우, 3 + 4 + 5 = 12이므로 12를 리턴합니다.

<br>
<br>

### 제한 사항

- a와 b가 같은 경우는 둘 중 아무 수나 리턴하세요.
- a와 b는 -10,000,000 이상 10,000,000 이하인 정수입니다.
- a와 b의 대소관계는 정해져있지 않습니다.

<br>

### 입출력 예

| a   | b   | return |
| --- | --- | ------ |
| 3   | 5   | 12     |
| 3   | 3   | 3      |
| 5   | 3   | 12     |

<br>

### 코드 작성

```js
function solution(a, b) {
  let sum = 0;
  if (a === b) return a;
  else {
    if (a > b) {
      let temp = a;
      a = b;
      b = temp;
    }
    for (let i = a; i <= b; i++) {
      sum += i;
    }
    return sum;
  }
}
```

<hr>
[ TIP ]<br>
주어진 두 수가 같으면 둘 중 하나를 리턴한다.<br>
주어진 두 수가 다르면 대소 관계를 확인하며 a에 작은 수를 b에 큰 수를 넣어준다.<br> 반목문으로 a ~ b 사이의 모든 숫자의 합을 구한다.
<br>
