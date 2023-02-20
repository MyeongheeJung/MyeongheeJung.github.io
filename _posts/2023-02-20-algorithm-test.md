---
layout: post
title: "[코딩테스트 연습] 수박수박수박수박수박수?"
subtitle: ""
categories: code
comments: true
---

## 수박수박수박수박수박수?

### 문제 설명

길이가 n이고, "수박수박수박수...."와 같은 패턴을 유지하는 문자열을 리턴하는 함수, solution을 완성하세요. 예를들어 n이 4이면 "수박수박"을 리턴하고 3이라면 "수박수"를 리턴하면 됩니다.

<br>

### 제한 사항

- n은 길이 10,000이하인 자연수입니다.

<br>

### 입출력 예

| n   | return     |
| --- | ---------- |
| 3   | "수박수"   |
| 4   | "수박수박" |

<br>

### 코드 작성

```js
function solution(n) {
  let answer = "";
  for (let i = 1; i <= n; i++) {
    i % 2 === 0 ? (answer += "박") : (answer += "수");
  }
  return answer;
}
```

<hr>
[ TIP ]<br>
주어진 길이를 확인하여 길이만큼 반복하면서 홀수일때 는 "수"를 짝수일때는 "박"을 더해 반환한다.

<br>
