---
layout: post
title: "[코딩테스트 연습] 약수의 합"
subtitle: ""
categories: code
comments: true
---

## 약수의 합

### 문제 설명

정수 n을 입력받아 n의 약수를 모두 더한 값을 리턴하는 함수, solution을 완성해주세요.
<br>

<br>

### 제한 사항

- n은 0 이상 3000이하인 정수입니다.

<br>

### 입출력 예 설명

입출력 예 #1<br>
12의 약수는 1, 2, 3, 4, 6, 12입니다. 이를 모두 더하면 28입니다.<br>

입출력 예 #2<br>
5의 약수는 1, 5입니다. 이를 모두 더하면 6입니다.

<br>

### 코드 작성

```js
function solution(n) {
  let answer = 0;
  for (i = 1; i <= n; i++) {
    if (n % i === 0) {
      answer += i;
    }
  }
  return answer;
}
```

<hr>

[ 약수 ]<br>
어떤 수나 식을 나누어 나머지가 없이 떨어지는 수나 식을 일컫는 말.
