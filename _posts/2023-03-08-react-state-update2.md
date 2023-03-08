---
layout: post
title: "[react] 상태의 배열 업데이트"
subtitle: ""
categories: react
comments: true
---

### 상태의 배열 업데이트

> state는 배열를 포함하여 모든 종류의 JavaScript 값을 보유할 수 있다.<br>
> 배열은 JavaScript에서 변경 가능하지만 state에 저장할 때는 변경 불가능한 것으로 취급해야 합니다.<br>
> React에서는 state의 배열를 직접 변경하지 않고 교체한다.<br>
> state에 저장된 배열을 업데이트하려면 새 배열을 만들고(또는 기존 배열의 복사본을 만든 다음) 새 배열을 사용하도록 state를 설정해야 한다.
> <br>

|      | 방지(배열을 변경)        | 선호 (새 배열 반환, 배열을 복사)          |
| ---- | ------------------------ | ----------------------------------------- |
| 추가 | push,unshift             | concat, [...arr]스프레드 구문             |
| 삭제 | pop, shift, splice       | filter, slice                             |
| 교체 | splice, arr[i] = 'vlaue' | map                                       |
| 정렬 | reverse,sort             | const newArr = [...arr] 배열 복사 후 변경 |

- slice VS splice
  - slice: 배열 또는 그 일부를 복사.
  - splice: 항목을 삽입하거나 삭제하기 위해 배열을 변경.

<hr>

## 배열을 변경하지 않고 추가하는 방법

```js
let nextId = 0;
const [artists, setArtists] = useState([]);

// 배열의 끝에 추가
setArtists([...artists, { id: nextId++, name: name }]);

// 배열의 앞에 추가
setArtists([{ id: nextId++, name: name }, ...artists]);
```

<br>

## 배열을 변경하지 않고 제거하는 방법

```js
import { useState } from "react";

let initialArtists = [
  { id: 0, name: "Marta Colvin Andrade" },
  { id: 1, name: "Lamidi Olonade Fakeye" },
  { id: 2, name: "Louise Nevelson" },
];

export default function List() {
  const [artists, setArtists] = useState(initialArtists);

  return (
    <>
      <ul>
        {artists.map((artist) => (
          <li key={artist.id}>
            {artist.name}
            <button
              onClick={() => {
                setArtists(artists.filter((a) => a.id !== artist.id));
              }}
            >
              Delete
            </button>
          </li>
        ))}
      </ul>
    </>
  );
}
```

<hr>

## 배열을 변경하지 않고 항목 바꾸기

```js
import { useState } from "react";

let initialCounters = [0, 0, 0];

export default function CounterList() {
  const [counters, setCounters] = useState(initialCounters);

  const handleIncrementClick = (index) => {
    const nextCounters = counters.map((c, i) => {
      if (i === index) {
        return c + 1;
      } else {
        return c;
      }
    });
    setCounters(nextCounters);
  };

  return (
    <ul>
      {counters.map((counter, i) => (
        <li key={i}>
          {counter}
          <button
            onClick={() => {
              handleIncrementClick(i);
            }}
          >
            +1
          </button>
        </li>
      ))}
    </ul>
  );
}
```

## 배열을 변경하지 않고 특정 위치에 항목 삽입

```js
import { useState } from "react";

let nextId = 3;
const initialArtists = [
  { id: 0, name: "Marta Colvin Andrade" },
  { id: 1, name: "Lamidi Olonade Fakeye" },
  { id: 2, name: "Louise Nevelson" },
];

export default function List() {
  const [name, setName] = useState("");
  const [artists, setArtists] = useState(initialArtists);

  function handleClick() {
    const insertAt = 1;
    const nextArtists = [
      ...artists.slice(0, insertAt),
      { id: nextId++, name: name },
      ...artists.slice(insertAt),
    ];
    setArtists(nextArtists);
    setName("");
  }

  return (
    <>
      <input value={name} onChange={(e) => setName(e.target.value)} />
      <button onClick={handleClick}>Insert</button>
      <ul>
        {artists.map((artist) => (
          <li key={artist.id}>{artist.name}</li>
        ))}
      </ul>
    </>
  );
}
```

<hr>
<br>

### 배열 내부의 객체 업데이트

- 중첩된 상태를 업데이트할 때 업데이트하려는 지점부터 최상위 수준까지 복사본을 만들어야 한다.

```js
import { useState } from "react";

let nextId = 3;
const initialTodos = [
  { id: 0, title: "Buy milk", done: true },
  { id: 1, title: "Eat tacos", done: false },
  { id: 2, title: "Brew tea", done: false },
];

export default function TaskApp() {
  const [todos, setTodos] = useState(initialTodos);

  function handleAddTodo(title) {
    setTodos([
      ...todos,
      {
        id: nextId++,
        title: title,
        done: false,
      },
    ]);
  }

  function handleChangeTodo(nextTodo) {
    setTodos(
      todos.map((t) => {
        if (t.id === nextTodo.id) {
          return nextTodo;
        } else {
          return t;
        }
      })
    );
  }

  function handleDeleteTodo(todoId) {
    setTodos(todos.filter((t) => t.id !== todoId));
  }

  return (
    <>
      <AddTodo onAddTodo={handleAddTodo} />
      <TaskList
        todos={todos}
        onChangeTodo={handleChangeTodo}
        onDeleteTodo={handleDeleteTodo}
      />
    </>
  );
}
```

## Immer로 배열 내부의 객체 간결한 업데이트 방법

- Immer를 사용하면 중첩된 객체의 사본을 쉽게 만들 수 있다.

Immer 라이브러리 사용하기

> npm install use-immer 설치
> import { useImmer } from 'use-immer' 추가하기

```js
let nextId = 3;
const initialTodos = [
  { id: 0, title: "Buy milk", done: true },
  { id: 1, title: "Eat tacos", done: false },
  { id: 2, title: "Brew tea", done: false },
];

export default function TaskApp() {
  const [todos, updateTodos] = useImmer(initialTodos);

  function handleAddTodo(title) {
    updateTodos((draft) => {
      draft.push({
        id: nextId++,
        title: title,
        done: false,
      });
    });
  }

  function handleChangeTodo(nextTodo) {
    updateTodos((draft) => {
      const todo = draft.find((t) => t.id === nextTodo.id);
      todo.title = nextTodo.title;
      todo.done = nextTodo.done;
    });
  }

  function handleDeleteTodo(todoId) {
    updateTodos((draft) => {
      const index = draft.findIndex((t) => t.id === todoId);
      draft.splice(index, 1);
    });
  }

  return (
    <>
      <AddTodo onAddTodo={handleAddTodo} />
      <TaskList
        todos={todos}
        onChangeTodo={handleChangeTodo}
        onDeleteTodo={handleDeleteTodo}
      />
    </>
  );
}
```
