---
layout: post
title: "[코딩테스트 연습] 자릿수 더하기"
subtitle: ""
categories: code
comments: true
---

## 자릿수 더하기

### 문제 설명

자연수 N이 주어지면, N의 각 자릿수의 합을 구해서 return 하는 solution 함수를 만들어 주세요.<br>
예를들어 N = 123이면 1 + 2 + 3 = 6을 return 하면 됩니다.
<br>

<br>

### 제한 사항

- N의 범위 : 100,000,000 이하의 자연수

<br>

### 입출력 예

| N   | answer |
| --- | ------ |
| 123 | 6      |
| 987 | 24     |

<br>

### 입출력 예 설명

입출력 예 #1<br>
문제의 예시와 같습니다.<br>

입출력 예 #2<br>
9 + 8 + 7 = 24이므로 24를 return 하면 됩니다.

<br>

### 코드 작성

```js
function solution(n) {
  let result = 0;
  const arr = String(n).split("");
  for (let i in arr) {
    result += Number(arr[i]);
  }
  return result;
}
```

<hr>

[ for...of ]<br>
for...of 명령문은 반복가능한 객체 (Array, Map, Set, String, TypedArray, arguments 객체 등을 포함)에<br>
대해서 반복하고 각 개별 속성값에 대해 실행되는 문이 있는 사용자 정의 반복 후크를 호출하는 루프를 생성한다.

<br>
<br>

[ TIP ]<br>
자연수를 문자로 타입 변환한 후 배열로 만든다.<br>
for-of 반복문을 사용하여 배열의 요소를 하나씩 추출하고,<br>
요소를 자연수로 다시 타입 변환한 뒤 합을 구한다.<br>
