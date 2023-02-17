---
layout: post
title: "[코딩테스트 연습] 없는 숫자 더하기"
subtitle: ""
categories: code
comments: true
---

## 없는 숫자 더하기

### 문제 설명

0부터 9까지의 숫자 중 일부가 들어있는 정수 배열 numbers가 매개변수로 주어집니다. numbers에서 찾을 수 없는 0부터 9까지의 숫자를 모두 찾아 더한 수를 return 하도록 solution 함수를 완성해주세요.

<br>

### 제한 사항

- 1 ≤ numbers의 길이 ≤ 9
  - 0 ≤ numbers의 모든 원소 ≤ 9
  - numbers의 모든 원소는 서로 다릅니다.

<br>

### 입출력 예

| numbers           | result |
| ----------------- | ------ |
| [1,2,3,4,6,7,8,0] | 14     |
| [5,8,4,0,6,7,9]   | 6      |

<br>

### 입출력 예 설명

입출력 예 #1<br>

- 5, 9가 numbers에 없으므로, 5 + 9 = 14를 return 해야 합니다.

<br>

입출력 예 #2<br>

- 1, 2, 3이 numbers에 없으므로, 1 + 2 + 3 = 6을 return 해야 합니다.

<br>

### 코드 작성

```js
function solution(numbers) {
  let answer = 0;
  for (let i = 0; i <= 9; i++) {
    if (!numbers.includes(i)) {
      answer += i;
    }
  }
  return answer;
}
```

<hr>
[ arr.includes() ]<br>
includes() 메서드는 배열이 특정 요소를 포함하고 있는지 판별한다.

<br>
