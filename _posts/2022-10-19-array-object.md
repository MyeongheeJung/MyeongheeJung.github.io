---
layout: post
title:  "[JavaScript] 배열과 객체"
subtitle:   ""
categories: js
comments: true
---

## 배열과 객체<br>
자바스크립트에서 여러개의 데이터를 한 곳에 보관하고, 편하게 접근하기 위해 사용하는 데이터 타입

- 프로퍼티란?
데이터 타입마다 가지고 있는 고유한 속성

- 메서드란? 해당 데이터가 특정한 동작을 하도록 기능을 가지고 있는 명령어

<br>

## 배열(Array)
1. 데이터를 순서와 함께 저장
2. [대괄호]로 생성 
3. 배열 안의 데이터를 요소(element)라고 한다. 
4. 각각의 요소는 쉼표로 구분
5. 데이터을 넣은 순서대로 0부터 시작하는 위치 데이터(index)를 가진다.
6. 배열 접근 방법: index 번호

```js
// 배열 생성
let makeArr = ["element0","element1","element2","element3"]

// 인덱스 번호로 요소에 접근하기
makeArr[2] 

// 결과 
"element2"


```

<br>

## 배열의 속성(Property)
array.length

특정 배열의 길이를 나타내는 속성(길이 = 배열 내 요소의 개수)

```js
let arr = ["여기는","우주","최강","코드","캠프"]
arr.length 

// 결과 
5
```
*** index 와는 다르게 length는 요소를 1번 부터 카운팅한다.

<br>

## 배열의 메서드(Method)

#### array.push(”추가할 데이터”)

배열의 가장 뒤의 데이터를 추가

```js
let colors = ["red","yellow","blue"]
colors.push("green")

// 결과
colors = ["red","yellow","blue","green"]

```

#### array.pop()

배열의 가장 뒤의 데이터를 삭제

push와는 다르게 pop의 괄호 안에는 데이터를 넣지 않아도 된다.

```js
let colors = ["red","yellow","blue"]
colors.pop()

// 결과
colors = ["red","yellow"]

```

#### array.includes("확인할 데이터")

특정 배열에 주어진 데이터가 포함되어있는지 확인.

포함되어 있는지에 따라 boolean값을 반환한다.

```js
let colors = ["red","yellow","blue"]
colors.includes("yellow")

// 결과
true
```

#### array.indexOf("찾을 데이터")

특정 배열에서 지정된 요소를 찾을 수 있는 첫 번째 인덱스를 반환. 

만일 찾을 수 없으면 -1을 반환한다.

```js
let colors = ["red","yellow","blue"]
colors.indexOf("red")

// 결과
0

```

<br>

## 객체(object)

1. 중괄호 {} 를 사용해서 정의
2. 내부의 요소는 프로퍼티(키 + 값)
3. 객체 접근 방법(. / [ ])
4. 두 가지 접근 방법으로 새로운 프로퍼티도 생성

<br>

## 객체의 속성(Property)
객체의 프로퍼티에 접근할 때는 기본적으로 key값에 접근해서 value를 가지고 온다.

#### Dot notation(점 표기법)
key값에 접근시, 점 . 을 이용해서 접근 하는 방법이다.

```js
const jasonData = {
  name: "jason",
  age: 25,
  gender: "Male"
}

jasonData.name // "jason"
jasonData.age  //  25

```
#### Bracket notation(괄호 표기법)

이 방법은 key값에 접근시, 대괄호 [] 를 이용해서 접근 하는 방법이다.

*** Bracket notation을 사용할 때 따옴표를 붙여주지 않으면, 안의 key값이 아닌 변수로 인식된다.

```js
const jasonData = {
  name: "jason",
  age: 25,
  gender: "Male"
}

jasonData["name"] // "jason"
jasonData["age"] // 25

```

<br>

## 객체의 메서드(Method)


#### Object.keys(객체 이름)

주어진 객체의 key 모음을 배열로(문자열로)

```js
const jasonData = {
  name: "jason",
  age: 25,
  gender: "Male"
}


Object.keys(jasonData)
// 결과 
[ "name", "age", "gender"]
```

#### Object.values(객체 이름)

주어진 객체의 value 모음을 배열로(데이터 그대로)

```js
const jasonData = {
  name: "jason",
  age: 25,
  gender: "Male"
}

Object.values(jasonData)
// 결과 
[ "jason", 25, "Male"]
```

