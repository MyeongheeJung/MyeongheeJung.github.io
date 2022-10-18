---
layout: post
title:  "[코딩테스트 연습] 중복된 문자 제거"
subtitle:   ""
categories: Code
comments: true
---


## 중복된 문자 제거

### 문제 설명
문자열 my_string이 매개변수로 주어집니다.<br>
my_string에서 중복된 문자를 제거하고 하나의 문자만 남긴 문자열을 return하도록 solution 함수를 완성해주세요.

<br>

### 제한 사항
- 1 ≤ my_string ≤ 1,000
- my_string은 대문자, 소문자, 공백으로 구성되어 있습니다.
- 대문자와 소문자를 구분합니다.
- 공백(" ")도 하나의 문자로 구분합니다.
- 중복된 문자 중 가장 앞에 있는 문자를 남깁니다.

<br>

### 입출력 예 설명
입출력 예 #1<br>
"people"에서 중복된 문자 "p"와 "e"을 제거한 "peol"을 return합니다.

입출력 예 #2<br>
"We are the world"에서 중복된 문자 "e", " ", "r" 들을 제거한 "We arthwold"을 return합니다.

<br>

### 코드 작성
```js
function solution(my_string) {
   const set = new Set(my_string.split(''))
   return [...set].join('')
}
```

<hr>

[ Set ]<br>
Set 객체는 자료형에 관계 없이 원시 값과 객체 참조 모두 유일한 값을 저장할 수 있다.
즉, 중복된 값이 있으면 한개만 유일하게 남겨준다.