---
layout: post
title: "[코딩테스트 연습] 문자열 내 마음대로 정렬하기"
subtitle: ""
categories: code
comments: true
---

## 문자열 내 마음대로 정렬하기

### 문제 설명

문자열로 구성된 리스트 strings와, 정수 n이 주어졌을 때, 각 문자열의 인덱스 n번째 글자를 기준으로 오름차순 정렬하려 합니다. 예를 들어 strings가 ["sun", "bed", "car"]이고 n이 1이면 각 단어의 인덱스 1의 문자 "u", "e", "a"로 strings를 정렬합니다.
<br>

### 제한 조건

- strings는 길이 1 이상, 50이하인 배열입니다.
- strings의 원소는 소문자 알파벳으로 이루어져 있습니다.
- strings의 원소는 길이 1 이상, 100이하인 문자열입니다.
- 모든 strings의 원소의 길이는 n보다 큽니다.
- 인덱스 1의 문자가 같은 문자열이 여럿 일 경우, 사전순으로 앞선 문자열이 앞쪽에 위치합니다.

<br>

### 입출력 예

| string                  | n   | return                  |
| ----------------------- | --- | ----------------------- |
| ["sun", "bed", "car"]   | 1   | ["car", "bed", "sun"]   |
| ["abce", "abcd", "cdx"] | 2   | ["abcd", "abce", "cdx"] |

<br>

### 입출력 예 설명

입출력 예1<br>
"sun", "bed", "car"의 1번째 인덱스 값은 각각 "u", "e", "a" 입니다. 이를 기준으로 strings를 정렬하면 ["car", "bed", "sun"] 입니다.
<br>

입출력 예2<br>
"abce"와 "abcd", "cdx"의 2번째 인덱스 값은 "c", "c", "x"입니다. 따라서 정렬 후에는 "cdx"가 가장 뒤에 위치합니다. "abce"와 "abcd"는 사전순으로 정렬하면 "abcd"가 우선하므로, 답은 ["abcd", "abce", "cdx"] 입니다.
<br>

### 코드 작성

```js
function solution(strings, n) {
  const sortS = strings.sort();
  const answer = sortS.sort((a, b) => {
    if (a[n] === b[n]) return 0;
    return a[n] < b[n] ? -1 : 1;
  });
  return answer;
}
```

<hr>

[ TIP ]<br>
주어진 strings 배열을 sort하여 사전순으로 정렬되게 만든다.
사전순으로 sort된 sortS에 n번째 글자를 기준으로 정렬되도록 조건을 작성하고 다시한번 sort해준다.
<br>

[ arr.sort() ]<br>
sort() 메서드는 배열의 요소를 적절한 위치에 정렬한 후 그 배열을 반환합니다. 기본 정렬 순서는 문자열의 유니코드 코드 포인트를 따른다.

- (a, b)이 0보다 작은 경우 a를 b보다 낮은 색인으로 정렬합니다. 즉, a가 먼저온다.
- (a, b)이 0을 반환하면 a와 b를 서로에 대해 변경하지 않고 모든 다른 요소에 대해 정렬한다.
- (a, b)이 0보다 큰 경우, b를 a보다 낮은 인덱스로 정렬한다.
  <br>
