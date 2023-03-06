---
layout: post
title: "[코딩테스트 연습] 시저 암호

"
subtitle: ""
categories: code
comments: true
---

## 시저 암호

### 문제 설명

어떤 문장의 각 알파벳을 일정한 거리만큼 밀어서 다른 알파벳으로 바꾸는 암호화 방식을 시저 암호라고 합니다. 예를 들어 "AB"는 1만큼 밀면 "BC"가 되고, 3만큼 밀면 "DE"가 됩니다. "z"는 1만큼 밀면 "a"가 됩니다. 문자열 s와 거리 n을 입력받아 s를 n만큼 민 암호문을 만드는 함수, solution을 완성해 보세요.
<br>

### 제한 사항

- 공백은 아무리 밀어도 공백입니다.
- s는 알파벳 소문자, 대문자, 공백으로만 이루어져 있습니다.
- s의 길이는 8000이하입니다.
- n은 1 이상, 25이하인 자연수입니다.

<br>

### 입출력 예

| s       | n   | result  |
| ------- | --- | ------- |
| "AB"    | 1   | "BC"    |
| "Z"     | 1   | "a"     |
| "a B z" | 4   | "e F d" |

<br>

### 코드 작성

```js
function solution(s, n) {
  let answer = "";

  for (let i = 0; i < s.length; i++) {
    if (s[i] === " ") {
      answer += " ";
      continue;
    }
    let code = s[i].charCodeAt() + n;
    if (code > 122 || (code > 90 && code - n <= 90)) {
      code -= 26;
    }
    answer += String.fromCharCode(code);
  }
  return answer;
}
```

<hr>

[ TIP ]<br>
주어진 문자 s의 길이만큼 반복문을 돌린다. 문자가 공백인 경우는 공백을 담아주고, n이 1이상 25인 자연수인 조건을 활용하여
문자가 'z', 'Z', 대문자일 경우에는 -26을 해준다.
<br>

[ str.charCodeAt(index) ]<br>
charCodeAt() 메서드는 주어진 인덱스에 대한 UTF-16 코드를 나타내는 0부터 65535 사이의 정수를 반환한다.

- index: 0 이상이고 문자열의 길이보다 작은 정수. 숫자가 아니라면 0을 기본값으로 사용함.
  <br>

[ String.fromCharCode() ]<br>
정적 String.fromCharCode()메서드는 지정된 UTF-16 코드 단위 시퀀스에서 생성된 문자열을 반환한다.

<br>
