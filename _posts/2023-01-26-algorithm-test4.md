---
layout: post
title: "[코딩테스트 연습] 평균 구하기"
subtitle: ""
categories: code
comments: true
---

## 평균 구하기

### 문제 설명

정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.
<br>

<br>

### 제한 사항

- arr은 길이 1 이상, 100 이하인 배열입니다.
- arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.

<br>

### 입출력 예

| arr       | return |
| --------- | ------ |
| [1,2,3,4] | 2.5    |
| [5,5]     | 5      |

<br>

### 코드 작성

```js
function solution(arr) {
  let result = 0;
  for (let i = 0; i < arr.length; i++) {
    result += arr[i];
  }
  return result / arr.length;
}
```

<br>

[ TIP ]<br>
반복문과 배열의 길이를 활용하여, 주어진 배열의 요소를 하나 씩 추출해 합을 구하고<br>
합을 배열의 길이로 나눠 평균을 구한다.
