---
layout: post
title: "[코딩테스트 연습] 가운데 글자 가져오기"
subtitle: ""
categories: code
comments: true
---

## 가운데 글자 가져오기

### 문제 설명

단어 s의 가운데 글자를 반환하는 함수, solution을 만들어 보세요. 단어의 길이가 짝수라면 가운데 두글자를 반환하면 됩니다.

<br>

### 제한 사항

- s는 길이가 1 이상, 100이하인 스트링입니다.

<br>

### 입출력 예

| s       | return |
| ------- | ------ |
| "abcde" | "c"    |
| "qwer"  | "we"   |

<br>

### 코드 작성

```js
function solution(s) {
  const mid = Math.floor(s.length / 2);
  return s.length % 2 === 0 ? s[mid - 1] + s[mid] : s[mid];
}
```

<hr>
[ Math.floor() ]<br>
Math.floor() 함수는 주어진 숫자와 같거나 주어진 수 이하의 가장 큰 정수를 반환한다.

<br>
