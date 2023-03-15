---
layout: post
title: "[JavaScript] 포커스와 해제 이벤트"
subtitle: ""
categories: js
comments: true
---

# 포커스와 해제 이벤트

- 이벤트가 버블링되지 않음
  - focus: 요소가 포커스를 받은 경우 이벤트 발생<br>
  - blur: 요소의 포커스가 해지될 때 이벤트 발생<br>
- 이벤트 버블링이 발생
  - focusin: 요소가 포커스를 받으면 이벤트가 발생
  - focusout: 요소가 포커스를 잃을 때 이벤트 발생<br>

<br>
<br>
<br>

# focus / focusin

#### HTML

```html
<form id="form">
  <label>
    Some text:
    <input type="text" placeholder="text input" />
  </label>
  <label>
    Password:
    <input type="password" placeholder="password" />
  </label>
</form>
```

#### 자바스크립트

```js
const password = document.querySelector('input[type="password"]');

password.addEventListener("focus", (event) => {
  event.target.style.background = "pink";
});

password.addEventListener("blur", (event) => {
  event.target.style.background = "";
});
```

<br>
<br>
<br>

# focusin / focusout

#### HTML

```html
<form id="form">
  <label>
    Some text:
    <input type="text" placeholder="text input" />
  </label>
  <label>
    Password:
    <input type="password" placeholder="password" />
  </label>
</form>
```

#### 자바스크립트

```js
const form = document.getElementById("form");

form.addEventListener("focusin", (event) => {
  event.target.style.background = "pink";
});

form.addEventListener("focusout", (event) => {
  event.target.style.background = "";
});
```
