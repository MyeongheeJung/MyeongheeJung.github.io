---
layout: post
title:  "[JavaScript] 원시타입과 참조타입"
subtitle:   ""
categories: js
comments: true
---


## 원시타입과 참조 타입
자바스크립트의 데이터타입은 크게 두가지 타입으로 나뉘게 됩니다.
바로 원시타입( Primitive type ) 과 참조타입( Refrence type ) 이다.

<br>

### 원시타입의 종류

String, Number, Boolean, Bigint, undefined, Symbol, null

<br>

### 원시타입의 특징
원시타입은 불변성을 가진다.<br>
불변성이란 변하지 않는 속성인데, 말 그대로 데이터가 변하지 않는 속성입니다.

```js
// 변수에 원시값을 재할당 시, 기존 원시값의 주소는 그대로 남아있다.
let box = 'abc'
// 변수 box는 새로운 주소값에 저당된 'def'로 할당된다.
box = 'def'
```

<br>

### 원시타입 갑의 복사
복사 시 해당 데이터가 담긴 메모리 주소를 그대로 전달
origin 값을 변경해도 copy 한 값에 영향을 주지 않는다.
```js
let origin = 'hi';
let copy = origin;
origin = 'bye';
console.log(copy); => hi
```

<br>


### 참조타입의 종류
원시타입을 제외한 나머지 모든 참조 타입이며, 참조타입은 객체타입이다 라고 봐도 무방하다.

<br>

### 참조타입의 특징
원시타입과 반대로 가변성 을 가지고 있습니다.

<br>

### 참조 타입 값의 복사
복사 시 해당 데이터가 담긴 메모리의 주소가 아닌, 참조 메모리의 주소를 전달
origin 값을 변경 시 copy 한 값이 같이 영향을 받는다.

```js
let origin = [1,2,3];
let copy = origin;
origin.pop();

console.log(copy); 
// 결과 [1,2]
console.log(origin);
// 결과 [1,2]
```


<hr>

비교 연산자

자바스크립트의 데이터를 서로 비교하는 방법
느슨한 비교 ==
데이터 값은 비교하지만, 타입은 비교하지 않는다.

엄격한 비교 ===
엄격한 비교연산자 는 값과 타입을 비교하는 것이 아닌, 
데이터의 메모리 주소를 비교 해 두 데이터가 완벽히 일치하는지 판단한다.

```
'1' == 1 
// 결과 true
'1' === 1
// 결과 false

let arr = [1, 2, 3]
arr === [1, 2, 3] 
// 결과 false, 값과 타입이 같아도 서로 주소 값이 다르므로 
```