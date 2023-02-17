---
layout: post
title: "[코딩테스트 연습] 제일 작은 수 제거하기"
subtitle: ""
categories: code
comments: true
---

## 제일 작은 수 제거하기

### 문제 설명

정수를 저장한 배열, arr 에서 가장 작은 수를 제거한 배열을 리턴하는 함수, solution을 완성해주세요. 단, 리턴하려는 배열이 빈 배열인 경우엔 배열에 -1을 채워 리턴하세요. 예를들어 arr이 [4,3,2,1]인 경우는 [4,3,2]를 리턴 하고, [10]면 [-1]을 리턴 합니다.

<br>

### 제한 사항

- arr은 길이 1 이상인 배열입니다.
- 인덱스 i, j에 대해 i ≠ j이면 arr[i] ≠ arr[j] 입니다.

<br>

### 입출력 예

| arr       | return  |
| --------- | ------- |
| [4,3,2,1] | [4,3,2] |
| [10]      | [-1]    |

<br>

### 코드 작성

```js
function solution(arr) {
  if (arr.length === 1) return [-1];
  const min = Math.min(...arr);
  return arr.filter((num) => num !== min);
}
```

<hr>
[ Math.min() ]<br>
Math.min() 함수는 주어진 숫자들 중 가장 작은 값을 반환한다.

<br>

[ ... Spread syntax ]<br>
전개 구문을 사용하면 배열이나 문자열과 같이 반복 가능한 문자를 0개 이상의 인수 또는 요소 로 확장하여, 0개 이상의 키-값의 쌍으로 객체로 확장시킬 수 있다.

<br>

[ arr.filter() ]<br>
filter() 메서드는 주어진 함수의 테스트를 통과하는 모든 요소를 모아 새로운 배열로 반환한다.
