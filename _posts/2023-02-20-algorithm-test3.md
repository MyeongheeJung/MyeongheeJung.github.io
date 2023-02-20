---
layout: post
title: "[코딩테스트 연습] 문자열 내림차순으로 배치하기"
subtitle: ""
categories: code
comments: true
---

## 문자열 내림차순으로 배치하기

### 문제 설명

문자열 s에 나타나는 문자를 큰것부터 작은 순으로 정렬해 새로운 문자열을 리턴하는 함수, solution을 완성해주세요.
s는 영문 대소문자로만 구성되어 있으며, 대문자는 소문자보다 작은 것으로 간주합니다.

<br>

### 제한 사항

- str은 길이 1 이상인 문자열입니다.

<br>

### 입출력 예

| s         | return    |
| --------- | --------- |
| "Zbcdefg" | "gfedcbZ" |

<br>

### 코드 작성

```js
function solution(s) {
  const arr = Array.from(s).sort((a, b) => (a > b ? -1 : 1));
  return arr.join("");
}
```

<hr>
[ arr.from() ]<br>
Array.from() 메서드는 유사 배열 객체나 반복 가능한 객체를 얕게 복사해 새로운Array 객체를 만든다.

<br>

[ arr.sort() ]<br>
sort() 메서드는 배열의 요소를 적절한 위치에 정렬한 후 그 배열을 반환합니다. 기본 정렬 순서는 문자열의 유니코드 코드 포인트를 따릅니다.

<br>

[ arr.join() ]<br>
join() 메서드는 배열의 모든 요소를 연결해 하나의 문자열로 만듭니다.

<br>
