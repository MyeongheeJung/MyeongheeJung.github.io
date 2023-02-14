---
layout: post
title: "[코딩테스트 연습] 정수 내림차순으로 배치하기"
subtitle: ""
categories: code
comments: true
---

## 정수 내림차순으로 배치하기

### 문제 설명

함수 solution은 정수 n을 매개변수로 입력받습니다. n의 각 자릿수를 큰것부터 작은 순으로 정렬한 새로운<br> 정수를 리턴해주세요. 예를들어 n이 118372면 873211을 리턴하면 됩니다.

<br>
<br>

### 제한 사항

- n은 1이상 8000000000 이하인 자연수입니다.

<br>

### 입출력 예

| n      | return |
| ------ | ------ |
| 118372 | 873211 |

<br>

### 코드 작성

```js
function solution(n) {
  const newArr = n.toString().split("");
  let answer = 0;
  let temp;
  for (let i = 0; i < newArr.length - 1; i++) {
    if (newArr[i] < newArr[i + 1]) {
      temp = newArr[i];
      newArr[i] = newArr[i + 1];
      newArr[i + 1] = temp;
      i = -1;
    }
  }
  answer = Number(newArr.join(""));
  return answer;
}
```

<hr>
[ TIP  ]<br>
주어진 정수 n을 문자열 배열로 변환한다.<br>
반복문을 활용하여 배열의 요소 앞 뒤를 비교하여, 뒤에 요소가 더 큰 값일 경우 temp 변수에 앞의 요소를 담아주고 자리를 바꿔준다.<br>
자리가 바뀔 경우 처음부터 반복하면서(i = -1) 가장 큰 수가 앞에 오게한다.<br>
배열에 담긴 값을 숫자로 변환한다.
<br>
sort((a,b) => b-a)를 활용하여 배열의 숫자를 큰 순으로 자동정렬 할 수 있으나, sort를 사용하지 않고 풀어보고 싶었다.
<br>

[ toString() ]<br>
toString() 은 문자열을 반환하는 object의 대표적인 방법이다.
<br>

[ split() ]<br>
split() 메서드는 String 객체를 지정한 구분자를 이용하여 여러 개의 문자열로 나눈다.
<br>

[ join() ]<br>
join() 메서드는 배열의 모든 요소를 연결해 하나의 문자열로 만든다.
<br>
