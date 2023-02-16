---
layout: post
title: "[코딩테스트 연습] 문자열 내 p와 y의 개수"
subtitle: ""
categories: code
comments: true
---

## 문자열 내 p와 y의 개수

### 문제 설명

대문자와 소문자가 섞여있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return 하는 solution를 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다.<br>
<br>
예를 들어 s가 "pPoooyY"면 true를 return하고 "Pyy"라면 false를 return합니다.

<br>
<br>

### 제한 사항

- 문자열 s의 길이 : 50 이하의 자연수<br>
- 문자열 s는 알파벳으로만 이루어져 있습니다.

<br>

### 입출력 예

| s         | answer |
| --------- | ------ |
| "pPoooyY" | true   |
| "Pyy"     | false  |

<br>

### 입출력 예 설명

입출력 예 #1<br>
'p'의 개수 2개, 'y'의 개수 2개로 같으므로 true를 return 합니다.<br>

입출력 예 #2<br>
'p'의 개수 1개, 'y'의 개수 2개로 다르므로 false를 return 합니다.

<br>

### 코드 작성

```js
function solution(s) {
  const strTolower = s.toLowerCase();
  let count = 0;

  for (let char of strTolower) {
    if (char === "p") {
      count += 1;
    }
    if (char === "y") {
      count -= 1;
    }
  }
  return count === 0 ? true : false;
}
```

<hr>
[ for...of  ]<br>
for...of 명령문은 반복가능한 객체 (Array, Map, Set, String, arguments 객체 등을 포함)에 대해서 반복하고 각 개별 속성값에 대해 실행되는 문을 반복 호출한다.
<br>
