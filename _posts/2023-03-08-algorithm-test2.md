---
layout: post
title: "[코딩테스트 연습] 두 개 뽑아서 더하기"
subtitle: ""
categories: code
comments: true
---

## 두 개 뽑아서 더하기

### 문제 설명

정수 배열 numbers가 주어집니다. numbers에서 서로 다른 인덱스에 있는 두 개의 수를 뽑아 더해서 만들 수 있는 모든 수를 배열에 오름차순으로 담아 return 하도록 solution 함수를 완성해주세요.

<br>

### 제한사항

- numbers의 길이는 2 이상 100 이하입니다.
  - numbers의 모든 수는 0 이상 100 이하입니다.

<br>

### 입출력 예

| numbers     | return        |
| ----------- | ------------- |
| [2,1,3,4,1] | [2,3,4,5,6,7] |
| [5,0,2,7]   | [2,5,7,9,12]  |

<br>

### 입출력 예 설명

입출력 예 #1<br>

- 2 = 1 + 1 입니다. (1이 numbers에 두 개 있습니다.)
- 3 = 2 + 1 입니다.
- 4 = 1 + 3 입니다.
- 5 = 1 + 4 = 2 + 3 입니다.
- 6 = 2 + 4 입니다.
- 7 = 3 + 4 입니다.
- 따라서 [2,3,4,5,6,7] 을 return 해야 합니다.

<br>

입출력 예 #2<br>

- 2 = 0 + 2 입니다.
- 5 = 5 + 0 입니다.
- 7 = 0 + 7 = 5 + 2 입니다.
- 9 = 2 + 7 입니다.
- 12 = 5 + 7 입니다.
- 따라서 [2,5,7,9,12] 를 return 해야 합니다.

<br>

### 코드 작성

```js
function solution(numbers) {
  let answer = [];
  numbers.map((_, i) =>
    numbers.map((_, k) => {
      if (i !== k) {
        answer = [...answer, numbers[i] + numbers[k]];
      }
    })
  );
  const result = new Set(answer);
  return [...result].sort((a, b) => a - b);
}
```

<hr>

[ TIP ]<br>
numbers 배열을 map 안에서 한번 더 map 돌리면서 index 값으로 같은 자리 수가 아닐 때의 합을 구해서 answer에 담아준다. new Set()을 사용하여 answer에 담긴 중복된 값을 제거해주고 sort로 정렬해준다.
<br>

[ Set 객체 ]<br>
원시값(string, number, bigint, bollean, undefined, symbol, null)과 객체 참조, 모든 유형의 유일한 값을 저장할 수 있다. 즉, Set 객체 내에 중복된 값이 있다면 한개만 유일하게 남겨준다.
<br>
