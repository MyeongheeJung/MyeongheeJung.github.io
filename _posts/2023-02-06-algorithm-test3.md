---
layout: post
title: "[코딩테스트 연습] 문자열을 정수로 바꾸기"
subtitle: ""
categories: code
comments: true
---

## 문자열을 정수로 바꾸기

### 문제 설명

문자열 s를 숫자로 변환한 결과를 반환하는 함수, solution을 완성하세요.

<br>
<br>

### 제한 사항

- s의 길이는 1 이상 5이하입니다.
- s의 맨앞에는 부호(+, -)가 올 수 있습니다.
- s는 부호와 숫자로만 이루어져있습니다.
- s는 "0"으로 시작하지 않습니다.

<br>

### 입출력 예

예를들어 str이 "1234"이면 1234를 반환하고, "-1234"이면 -1234를 반환하면 됩니다.<br>
str은 부호(+,-)와 숫자로만 구성되어 있고, 잘못된 값이 입력되는 경우는 없습니다.<br>

<br>

### 코드 작성

```js
function solution(s) {
  return Number(s);
}
```

```js
function solution(s) {
  return parseInt(s);
}
```

<hr>
[ Number() 생성자 ]<br>
Number() 생성자는 Number 객체를 생성한다.<br>
<br>

parseInt()<br>
parseInt() 함수는 문자열 인자를 파싱하여 특정 진수(수의 진법 체계에서 기준이 되는 값)의 정수를 반환합니다.<br>
