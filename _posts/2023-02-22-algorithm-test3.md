---
layout: post
title: "[코딩테스트 연습] 직사각형 별찍기"
subtitle: ""
categories: code
comments: true
---

## 직사각형 별찍기

### 문제 설명

이 문제에는 표준 입력으로 두 개의 정수 n과 m이 주어집니다.
별(\*) 문자를 이용해 가로의 길이가 n, 세로의 길이가 m인 직사각형 형태를 출력해보세요.

<br>

### 제한 사항

- n과 m은 각각 1000 이하인 자연수입니다.

<br>

### 예시

##### 입력

> 5 3

##### 츨력

> '\*\*\*\*\*'
> '\*\*\*\*\*'
> '\*\*\*\*\*'

<br>

### 코드 작성

```js
process.stdin.setEncoding("utf8");
process.stdin.on("data", (data) => {
  const n = data.split(" ");
  const a = Number(n[0]),
    b = Number(n[1]);
  for (let i = 0; i < b; i++) {
    console.log("*".repeat(a));
  }
});
```

<hr>
[ str.repeat(count) ]<br>
repeat() 메서드는 문자열을 주어진 횟수만큼 반복해 붙인 새로운 문자열을 반환한다.

- count: 문자열을 반복할 횟수. 0과 양의 무한대 사이의 정수([0, +∞)).

<br>
