---
layout: post
title: "[코딩테스트 연습] 나누어 떨어지는 숫자 배열"
subtitle: ""
categories: code
comments: true
---

## 나누어 떨어지는 숫자 배열

### 문제 설명

array의 각 element 중 divisor로 나누어 떨어지는 값을 오름차순으로 정렬한 배열을 반환하는 함수, solution을 작성해주세요.
divisor로 나누어 떨어지는 element가 하나도 없다면 배열에 -1을 담아 반환하세요.

<br>

### 제한 사항

- arr은 자연수를 담은 배열입니다.
- 정수 i, j에 대해 i ≠ j 이면 arr[i] ≠ arr[j] 입니다.
- divisor는 자연수입니다.
- array는 길이 1 이상인 배열입니다.

<br>

### 입출력 예

| arr           | divisor | return        |
| ------------- | ------- | ------------- |
| [5, 9, 7, 10] | 5       | [5,10]        |
| [2, 36, 1, 3] | 1       | [1, 2, 3, 36] |
| [3,2,6]       | 10      | [-1]          |

<br>

### 입출력 예 설명

입출력 예 #1<br>
arr의 원소 중 5로 나누어 떨어지는 원소는 5와 10입니다. 따라서 [5, 10]을 리턴합니다.<br>

입출력 예 #2<br>
arr의 모든 원소는 1으로 나누어 떨어집니다. 원소를 오름차순으로 정렬해 [1, 2, 3, 36]을 리턴합니다.<br>

입출력 예 #3<br>
3, 2, 6은 10으로 나누어 떨어지지 않습니다. 나누어 떨어지는 원소가 없으므로 [-1]을 리턴합니다.<br>

<br>

### 코드 작성

```js
function solution(arr, divisor) {
  const newArr = arr.filter((el) => el % divisor === 0);
  const answer = newArr.length === 0 ? [-1] : newArr.sort((a, b) => a - b);
  return answer;
}
```

<hr>
[ arr.filter() ]<br>
filter() 메서드는 주어진 함수의 테스트를 통과하는 모든 요소를 모아 새로운 배열로 반환한다.

<br>
[ arr.sort(compareFunction) ]<br>
sort() 메서드는 배열의 요소를 적절한 위치에 정렬한 후 그 배열을 반환합니다.<br>
기본 정렬 순서는 문자열의 유니코드 코드 포인트를 따릅니다.<br>
- compareFunction(옵션) :
  - compareFunction이 제공되지 않으면 요소를 문자열로 변환하고 유니 코드 코드 포인트 순서로 문자열을 비교하여 정렬한다. (숫자 정렬에서는 9가 80보다 앞에 오지만 숫자는 문자열로 변환되기 때문에 "80"은 유니 코드 순서에서 "9"앞에 온다.)
  - compareFunction이 제공되면 배열 요소는 compare 함수의 반환 값에 따라 정렬된다. a와 b가 비교되는 두 요소라면, compareFunction(a, b)이 0보다 작은 경우 a를 b보다 낮은 색인으로 정렬한다. 즉, a가 먼저온다.
