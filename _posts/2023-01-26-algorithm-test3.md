---
layout: post
title: "[코딩테스트 연습] 짝수와 홀수"
subtitle: ""
categories: code
comments: true
---

## 짝수와 홀수

### 문제 설명

정수 num이 짝수일 경우 "Even"을 반환하고 홀수인 경우 "Odd"를 반환하는 함수, solution을 완성해주세요.
<br>

<br>

### 제한 사항

- num은 int 범위의 정수입니다.
- 0은 짝수입니다.

<br>

### 입출력 예

| num | return |
| --- | ------ |
| 3   | "Odd"  |
| 4   | "Even" |

<br>

### 코드 작성

```js
function solution(num) {
  return num % 2 === 0 ? "Even" : "Odd";
}
```

<hr>

[ 나머지 연산자(%) ]<br>
나머지 연산자(%)는 왼쪽 피연산자를 오른쪽 피연산자로 나눴을 때의 나머지를 구한다.<br>
부호는 항상 왼쪽 피연산자의 부호를 따릅니다.

<br>
<br>

[ TIP ]<br>
나머지 연산자를 활용하여, 주어진 정수를 2로 나눴을 때 나머지 여부로 "짝수"인지 "홀수"를 판별한다.<br>
