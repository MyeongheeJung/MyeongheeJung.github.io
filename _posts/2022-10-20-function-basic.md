---
layout: post
title: "[JavaScript] 함수 사용하기"
subtitle: ""
categories: js
comments: true
---

## 함수

어떠 기능을 수행하거나 계산을 수행할 수 있도록 하는 코드의 집합<br>
함수를 통해 원하는 기능을 만들어 필요한 곳에서 사용할 수 있다.

- 전달인자<br>
  함수의 외부에서 데이터를 전달

- 매개변수(parameter)<br>
  함수를 선언할 때, 소괄호 안에 정의되는 변수
  외부에서 인자로 전달 받은 데이터를 내부에서 매개변수로 활용

- 반환데이터(return 값)<br>
  상자에서 반환되어 나오는 값. 결과데이터 라고 한다.
  함수가 실행되는 와중에 return 명령어를 만나게 되면 해당 함수를 종료시킨다.

      ❗️매개변수(parameter)와 return 값은 필수가 아니다.<br>

  매개변수와 리턴값은 있어도 되고 없어도 되는 값이기 때문에 필요할 때 적절히 적어주면 된다.

- 함수의 호출<br>
  함수를 사용하기 위해서는 함수 이름, 변수명 뒤에 ()를 붙여 호출해 준다.

```js
function Name(매개변수) {
  return 반환데이터;
}
// 함수를 사용하기위한 호출
Name(전달인자);

const Name = function (매개변수) {
  return 반환데이터;
};
// 함수를 사용하기위한 호출
Name(전달인자);
```

<br>

## 함수 선언 종류

### 함수의 선언문

function 함수이름(param1, param2, ...){
// ...code here
return 결과값
}
함수 표현식의 함수는 기명함수라고 부른다.
함수선언식의 기명함수는 호이스팅의 영향을 받는다.

<br>

### 함수의 표현식

const 함수이름 = function(param1, param2, ...){
// ...code here
return 결과값
}

함수 표현식의 함수는 익명함수라고 부른다.
함수 표현식의 익명함수는 호이스팅의 영향을 받지 않는다.

<br>

### 화살표 함수

const 함수이름 = ( param1, param2, ... )=>{
// ...code here
return 결과값
}
화살표 함수는 호이스팅의 영향을 받지 않는다.

\*\*\* 호이스팅
브라우저가 자바스크립트를 해석하는 과정에서 코드가 최상단으로 끌어올려진 것 처럼 동작한다.
선언문으로 작성된 함수는 선언 이전에 사용할 수 있다.(호이스팅의 영향 받음)
표현식은 선언 이전에 함수를 사용하게되면 에러가 발생한다.(호이스팅의 영향 받지 않음)
화살표 함수는 표현식과 같이 동작

<br>

### 함수 사용 예시: D-day 구하기

```html
<!-- html -->
<input id="target-year-input" class="targer-input" />
<input id="target-month-input" class="target-input" />
<input id="target-date-input" class="target-input" />
<button onclick="counterMaker()">버튼</button>
```

```js
const dateFormMaker = function () {
  // querySelector() 사용하여 htmld의 요소 참조
  const inputYear = document.querySelector("#target-year-input").value;
  const inputMonth = document.querySelector("#target-month-input").value;
  const inputDate = document.querySelector("#target-date-input").value;
  const dateFormat = `${inputYear}-${inputMonth}-${inputDate}`;
  // input tag에 작성된 값들 반환
  return dateFormat;
};

const counterMaker = () => {
  // dateFormMaker 함수 호출 => return으로 반환된 값이 targetDateInput에 담긴다.
  const targetDateInput = dateFormMaker();

  // new Date()를 사용해서 날짜, 시간 가져오기
  const nowDate = new Date();
  const targetDate = new Date(targetDateInput).setHours(0, 0, 0, 0);
  const remaining = (targetDate - nowDate) / 1000;
  const remainingDate = Math.floor(remaining / 3600 / 24);
  const remainingHours = Math.floor(remaining / 3600) % 24;
  const remainingMin = Math.floor(remaining / 60) % 60;
  const remainingSec = Math.floor(remaining) % 60;

  console.log(remainingDate, remainingHours, remainingMin, remainingSec);
};
```

- querySelector()<br>
  JavaScript 내에서 HTML의 요소를 참조한다.

- new Date()<br>
  자바스크립트에서의 날짜 데이터는 일종의 객체로 관리되고,<br>
  new Date()를 사용해서 사용자의 컴퓨터 시간을 기준으로 현재 날짜, 시간을 모두 가져올 수 있다.<br>
  new Date("2022-09-09") 이런식으로 날짜를 지정해주면, 특정 날짜의 데이터도 받아올 수 있다.

- setHours(0,0,0,0)
  가장 가까운 자정으로 시간 변경
