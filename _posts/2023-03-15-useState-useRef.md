---
layout: post
title: "[react] 제어 컴포넌트와 비제어 컴포넌트"
subtitle: ""
categories: react
comments: true
---

# 제어 컴포넌트와 비제어 컴포넌트

HTML에서 input, textarea, select와 같은 폼 엘리먼트는 일반적으로 사용자의 입력을 기반으로 자신의 state를 관리하고 업데이트한다.<br>
리액트에서는 같은 폼 엘리먼트라도 "제어 컴포넌트" 방식과 "비제어 컴포넌트" 방식으로 만들 수 있다.

<br>
<br>
<br>

### 제어 컴포넌트

```js
function ControlledInput() {
  const [inputValue, setInputValue] = useState('')

  return (
    <>
    <input type="text" value={inputValue}
    onChange={(e) => setInputValue(e.target.value)} />
    <button onClick={(() => console.log(inputValue))}></button>
  )
}
```

> useState로 폼에 발생하는 사용자 입력값을 다루는 방식을 “제어 컴포넌트"라고 한다.

<br>
<br>

<br>

### 비제어 컴포넌트

```js
function UncontrolledInput() {
  const inputRef = useRef(null)

  return (
    <>
    <input type="text" ref={inputRef} />
    <button onClick={(() => console.log(inputRef.current.value))}></button>
  )
}
```

> useRef를 활용하여 DOM 자체에서 폼을 다루는 방식을 “비제어 컴포넌트"라고 한다.
