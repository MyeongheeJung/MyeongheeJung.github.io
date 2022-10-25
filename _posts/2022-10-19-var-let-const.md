---
layout: post
title: "[JavaScript] 변수와 상수"
subtitle: ""
categories: js
comments: true
---

# 변수와 상수

자바스크립트에서는 데이터를 다루기 위해 변수와 상수를 사용 한다. 변수와 상수는 데이터를 재사용하고, 해당 데이터에 접근하기 위해 필요하다.

변수 (값이 변할 수 있음) : var , let
상수 (값이 변할 수 없음) : const

<br>

# 선언과 할당

### 선언(declaration)

선언은 변수와 상수를 사용하기 위해 변수의 이름을 알려주는 행위

[ 변수명 작성 시 주의사항 ]<br>

- 변수명은 동사가 아닌 명사로
- 첫 글자는 숫자 사용 불가능
- 예약어를 제외한 변수명을 선언해야 한다.
- camelCase 사용

```js
let result;
// let이라는 키워드를 이용해 result 라는 변수를 생성
```

<br>

### 할당(definition)

할당 이란 변수에 데이터를 담아주는 행위
변수에 데이터를 할당하게 되면, 할당된 데이터는 컴퓨터의 메모리에 저장된다.

\*\*\* 자바스크립트의 등호(=)는 같다의 의미가 아닌 할당의 의미!

```js
result = 10 + 20;
// result라는 변수에 10+20 라는 데이터를 담는다.
```

<br>

### 선언 + 할당

```js
let result = 10 + 20;
//선언부    //할당부
```

<br>

### 변수 참조

```js
console.log(result);
// 변수 result를 호출하면, 30이 결과로 반환된다.
```

<br>

## 변수 키워드에 따른 차이점

| 변수명                   | var     | let     | const  |
| ------------------------ | ------- | ------- | ------ |
| 재선언 여부(변수명 중복) | 가능⭕️ | 불가❌  | 불가❌ |
| 재할당 여부(데이터 수정) | 가능⭕️ | 가능⭕️ | 불가❌ |

<br>
<br>

## 스코프scope

변수 참조의 유효 범위를 말한다.

[ 전역 스코프 global scope ]

```js
let x = 0;
let y = 0;

const scopeTest = () => {
  let z = 2;
  console.log(x);
  console.log(y);
};

console.log(z);
```

[ 지역 스코프 local scope ]

- 함수 레벨 스코프 : var 키워드

```js
const sum = () => {
  var x = 0;
};
```

<br>

- 블록 레벨 스코프 : let & const 키워드, 중괄호로 선어된 문

```js
if() {
let y = 0;
}
```
