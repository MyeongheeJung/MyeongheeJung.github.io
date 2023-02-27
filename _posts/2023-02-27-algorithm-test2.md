---
layout: post
title: "[코딩테스트 연습] 이상한 문자 만들기
"
subtitle: ""
categories: code
comments: true
---

## 이상한 문자 만들기

### 문제 설명

문자열 s는 한 개 이상의 단어로 구성되어 있습니다. 각 단어는 하나 이상의 공백문자로 구분되어 있습니다. 각 단어의 짝수번째 알파벳은 대문자로, 홀수번째 알파벳은 소문자로 바꾼 문자열을 리턴하는 함수, solution을 완성하세요.

<br>

### 제한 사항

- 문자열 전체의 짝/홀수 인덱스가 아니라, 단어(공백을 기준)별로 짝/홀수 인덱스를 판단해야합니다.
- 첫 번째 글자는 0번째 인덱스로 보아 짝수번째 알파벳으로 처리해야 합니다.

<br>

### 입출력 예

| s                 | return            |
| ----------------- | ----------------- |
| "try hello world" | "TrY HeLlO WoRlD" |

<br>

### 입출력 예 설명

"try hello world"는 세 단어 "try", "hello", "world"로 구성되어 있습니다. 각 단어의 짝수번째 문자를 대문자로, 홀수번째 문자를 소문자로 바꾸면 "TrY", "HeLlO", "WoRlD"입니다. 따라서 "TrY HeLlO WoRlD" 를 리턴합니다.

<br>

### 코드 작성

```js
function solution(s) {
  let answer = "";
  const arr = s.toLowerCase().split(" ");
  for (let i = 0; i < arr.length; i++) {
    for (let k = 0; k < arr[i].length; k++) {
      answer += k % 2 === 0 ? arr[i][k].toUpperCase() : arr[i][k];
    }
    if (i !== arr.length - 1) answer += " ";
  }
  return answer;
}
```

<hr>
[ TIP ]<br>
주어진 문자열 s를 모두 소문자로 변환 후, 공백문자를 활용하여 배열로 변환한다. 배열 안에 담긴 str을 하나 씩 추출하고 str의 index값을 활용해 짝수인 경우 대문자로 변환하여 answer에 담아준다.<br>
str 사이의 공백문자는 배열의 길이를 확인하여 마지막 요소가 아닌 경우에 공백을 추가해줬다.
<br>

[ str.toLowerCase()() ]<br>
메서드 toLowerCase()는 소문자로 변환된 호출 문자열 값을 반환한다.

<br>

[ str.toUpperCase() ]<br>
메서드 toUpperCase()는 대문자로 변환된 호출 문자열 값을 반환한다.
