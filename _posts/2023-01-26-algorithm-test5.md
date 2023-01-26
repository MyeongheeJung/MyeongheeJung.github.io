---
layout: post
title: "[코딩테스트 연습] 자연수 뒤집어 배열로 만들기"
subtitle: ""
categories: code
comments: true
---

## 자연수 뒤집어 배열로 만들기

### 문제 설명

자연수 n을 뒤집어 각 자리 숫자를 원소로 가지는 배열 형태로 리턴해주세요.<br>
예를들어 n이 12345이면 [5,4,3,2,1]을 리턴합니다.
<br>

<br>

### 제한 사항

- n은 10,000,000,000이하인 자연수입니다.

<br>

### 입출력 예

| n     | return      |
| ----- | ----------- |
| 12345 | [5,4,3,2,1] |

<br>

### 코드 작성

```js
function solution(n) {
  let result = [];
  const arr = String(n).split("");
  for (let i = arr.length - 1; i >= 0; i--) {
    result.push(Number(arr[i]));
  }
  return result;
}
```

<br>

[ split() ]<br>
split() 메서드는 String 객체를 지정한 구분자를 이용하여 여러 개의 문자열로 나눈다.<br>
\*\*\* Array.from()을 사용해서 문자열을 배열로 변환할 수 있다.<br>
--- (ex) Array.from('12345') => ['1', '2', '3', '4', '5']

<br>
<br>

[ push() ]<br>
push() 메서드는 배열의 끝에 하나 이상의 요소를 추가하고, 배열의 새로운 길이를 반환합니다.

<br>
<br>

[ TIP ]<br>
자연수를 문자 타입으로 변환 후 배열로 만들어 주고,<br>
반목문을 활용하여 뒤에서 부터 배열의 요소를 추출한다.<br>
추출된 배열의 요소를 자연수로 변환 후 새로운 배열에 담아준다.
