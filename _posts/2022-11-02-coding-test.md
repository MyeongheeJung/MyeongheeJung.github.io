---
layout: post
title: "[코딩테스트 연습] 며칠"
subtitle: ""
categories: code
comments: true
--

## 며칠

### 문제 설명

입력되는 달(month)에 따라 각 달에 며칠이 있는지 보여주는 함수를 만들려고 합니다.<br>
각 조건에 해당하는 알맞은 값을 입력해주세요.

<br>

### 제한 사항

- month는 1~12의 숫자

<br>

### 입출력 예 설명

입출력 예 #1<br>
days(1) // 31

입출력 예 #2<br>
days(2) // 28

입출력 예 #4<br>
days(4) // 30


<br>

### 코드 작성

```js
function days(month) {
  let days = "";
  switch (month) {
    case 1:
      days = "31일";
      break;
    case 2:
      days = "28일";
      break;
    case 3:
      days = "31일";
      break;
    case 4:
      days = "30일";
      break;
    case 5:
      days = "31일";
      break;
    case 6:
      days = "30일";
      break;
    case 7:
      days = "31일";
      break;
    case 8:
      days = "31일";
      break;
    case 9:
      days = "30일";
      break;
    case 10:
      days = "31일";
      break;
    case 11:
      days = "30일";
      break;
    case 12:
      days = "31일";
      break;
  }
  return days;
}

```

<hr>

### 참고하면 좋은 코드 작성법

```js
const monthList = {
  1: 31,
  2: 28,
  3: 31,
  4: 30,
  5: 31,
  6: 30,
  7: 31,
  8: 31,
  9: 30,
  10: 31,
  11: 30,
  12: 31,
};

function days(month) {
  return monthList[month];
}
```

쉬운 문제이나, 객체의 "key - value"를 활용하여 답을 도출하는 게 더 간편하기 때문에 기록으로 남긴다.
