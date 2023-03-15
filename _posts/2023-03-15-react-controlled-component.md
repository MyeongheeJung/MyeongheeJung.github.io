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

> 제어 컴포넌트 : React에 의해 값이 제어되는 폼 엘리먼트

- 사용자 입력 이벤트 발생<br>
- 이벤트 헨들러에서 setState로 state 변경<br>
- 변경된 state를 바탕으로 React가 엘리먼트를 리렌더

<br>

> 비제어 컴포넌트 : React에 의해 값이 제어되지 않는 폼 엘리먼트

- 사용자 입력 이벤트 발생
- DOM 엘리먼트의 상태 직접 변경

<br>
<br>
<br>
<br>

# 제어 컴포넌트

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

제어 컴포넌트의 경우, react가 상태를 관리하므로 state가 변경될 때마다 그 값을 바탕으로 DOM이 새롭게 렌더링 된다. 즉, React에서는 항상 실시간으로 최신 상태를 유지할 수 있다. 이렇듯 React에서 컴포넌트 상태에 대한 완전한 주도권을 가지고 있기 때문에 세부적인 Form 조작이 편리하다.

<br>
<br>
<br>
<br>

# 비제어 컴포넌트

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

Form이 간단하고, 실시간으로 이루어져야 하는 작업이 없다면 구태여 제어 컴포넌트를 이용할 필요는 없다. 일반적인 Form의 방식대로 비제어 컴포넌트로 사용하는 것이 더 심플하고 성능이 좋은 방법일 수 있다.
