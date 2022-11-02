---
layout: post
title: "[JavaScript] Array.filter() 활용하기"
subtitle: ""
categories: js
comments: true
---

## Array.filter <br>

filter() 메서드는 주어진 함수의 테스트를 통과하는 모든 요소를 모아 새로운 배열을 반환한다.

<br>
<br>

case 1) 모든 작은 값 걸러내기<br>
다음 예는 값이 10 이하인 모든 요소가 제거된 걸러진 배열을 만들기 위해 filter()를 사용합니다.

```js
const numbers = [12, 5, 8, 130, 44];

const filtered = numbers.filter((v) => v >= 10);

console.log(filterd); // [12, 130, 44]
```

<br>
<br>

case 2) 배열 내용 검색<br>
다음 예는 배열 내용을 조건에 따라 검색하기 위해 filter() 를 사용합니다.

```js
const fruits = ["apple", "banana", "grapes", "mango", "orange"];

const filterItems = (text) => {
  return fruits.filter(
    (el) => el.toLowerCase().indexOf(text.toLowerCase()) > -1
  );
};

console.log(filterItems("ap")); // ['apple', 'grapes']
console.log(filterItems("an")); // ['banana', 'mango', 'orange']
```

<br>
<br>

case 3) JSON에서 무효한 항목 거르기<br>
다음 예는 0이 아닌, 숫자 id인 모든 요소의 걸러진 json을 만들기 위해 filter()를 사용합니다.

```js
const arr = [
  { id: 15 },
  { id: -1 },
  { id: 0 },
  { id: 3 },
  { id: 12.2 },
  {},
  { id: null },
  { id: NaN },
  { id: "undefined" },
];

var invalidEntries = 0;

const isNumber = (obj) => {
  return obj !== undefined && typeof obj === "number" && !isNaN(obj);
};

const filterByID = (item) => {
  if (isNumber(item.id) && item.id !== 0) {
    return true;
  }
  invalidEntries++;
  return false;
};

var arrByID = arr.filter(filterByID);

console.log("Filtered Array", arrByID);
// Filtered Array
// [{ id: 15 }, { id: -1 }, { id: 3 }, { id: 12.2 }]

console.log("Number of Invalid Entries = ", invalidEntries);
// Number of Invalid Entries = 5
```

[※ 참고: MDN 기술서](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Array/filter#%EB%B0%B0%EC%97%B4_%EB%82%B4%EC%9A%A9_%EA%B2%80%EC%83%89)

<hr>

##### filter 사용하면 좋은 알고리즘 문제모음

- [같은 숫자는 싫어](https://school.programmers.co.kr/learn/courses/30/lessons/12906)
- [제일 작은 수 제거하기](https://school.programmers.co.kr/learn/courses/30/lessons/12935)
