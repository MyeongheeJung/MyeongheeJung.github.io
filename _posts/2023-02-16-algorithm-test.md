---
layout: post
title: "[코딩테스트 연습] 서울에서 김서방 찾기"
subtitle: ""
categories: code
comments: true
---

## 서울에서 김서방 찾기

### 문제 설명

String형 배열 seoul의 element중 "Kim"의 위치 x를 찾아, "김서방은 x에 있다"는 String을 반환하는 함수, solution을<br> 완성하세요. seoul에 "Kim"은 오직 한 번만 나타나며 잘못된 값이 입력되는 경우는 없습니다.

<br>
<br>

### 제한 사항

- seoul은 길이 1 이상, 1000 이하인 배열입니다.
- seoul의 원소는 길이 1 이상, 20 이하인 문자열입니다.
- "Kim"은 반드시 seoul 안에 포함되어 있습니다.

<br>

### 입출력 예

| seoul           | return              |
| --------------- | ------------------- |
| ["Jane", "Kim"] | "김서방은 1에 있다" |

<br>

### 코드 작성

```js
function solution(seoul) {
  const index = seoul.indexOf("Kim");
  return `김서방은 ${index}에 있다`;
}
```

<hr>
[ arr.indexOf(searchElement, (fromIndex)) ]<br>
indexOf() 메서드는 배열에서 지정된 요소를 찾을 수 있는 첫 번째 인덱스를 반환하고 존재하지 않으면 -1을 반환한다.

- searchElement : 배열에서 찾을 요소
- fromIndex(옵션): 검색을 시작할 색인, 기본값 0.

```js
var array = [2, 9, 9];
array.indexOf(2); // 0
array.indexOf(7); // -1
array.indexOf(9, 2); // 2
array.indexOf(2, -1); // -1
array.indexOf(2, -3); // 0
```

<br>
