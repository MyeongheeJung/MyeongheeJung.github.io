---
layout: post
title: "[코딩테스트 연습] 핸드폰 번호 가리기"
subtitle: ""
categories: code
comments: true
---

## 핸드폰 번호 가리기

### 문제 설명

프로그래머스 모바일은 개인정보 보호를 위해 고지서를 보낼 때 고객들의 전화번호의 일부를 가립니다. 전화번호가 문자열 phone_number로 주어졌을 때, 전화번호의 뒷 4자리를 제외한 나머지 숫자를 전부 \*으로 가린 문자열을 리턴하는 함수, solution을 완성해주세요.

<br>

### 제한 사항

- phone_number는 길이 4 이상, 20이하인 문자열입니다.

<br>

### 입출력 예

| phone_number  | return               |
| ------------- | -------------------- |
| "01033334444" | "\*\*\*\*\*\*\*4444" |
| "027778888"   | "\*\*\*\*\*8888"     |

<br>

### 코드 작성

```js
function solution(phone_number) {
  let answer = "";
  for (let i = 0; i < phone_number.length; i++) {
    if (i < phone_number.length - 4) {
      answer += "*";
    } else {
      answer += phone_number[i];
    }
  }
  return answer;
}
```

<hr>
[ TIP ]<br>
반복문과 문자의 길이를 활용하여 가려야 할 부분은 '*'로 안가리는 부분은 그대로 answer 변수에 담아준다.

<br>
