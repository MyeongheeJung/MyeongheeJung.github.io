---
layout: post
title: "[react] 상태 관리: 객체 업데이트, Immer 사용하기"
subtitle: ""
categories: react
comments: true
---

### 객체로 작성된 state 업데이트

> state는 객체를 포함하여 모든 종류의 JavaScript 값을 보유할 수 있다.<br>
> 객체는 JavaScript에서 변경 가능하지만 state에 저장할 때는 변경 불가능한 것으로 취급해야 한다.<br>
> React에서는 state의 객체를 직접 변경하지 않고 교체한다.<br>
> state에 저장된 객체를 업데이트하려면 새 객체를 생성(또는 기존 객체의 복사본을 만든 다음) 해당 복사본을 사용하도록 state를 설정해야 한다.
> <br>

```js
const [position, setPosition] = useState({
  x: 0,
  y: 0,
});

// 이 코드는 상태에서 기존 객체를 수정하기 때문에 문제가 된다.
// React에서는 상태에 넣은 모든 JavaScript 객체를 읽기 전용으로 취급해야 한다.
// 변경하는 대신 항상 교체해야 한다.
position.x = e.clientX;
position.y = e.clientY;

// 새 객체 생성 후 set 함수에 전달
const nextPosition = {};
nextPosition.x = e.clientX;
nextPosition.y = e.clientY;
setPosition(nextPosition);

// set 함수로 객체 교체
setPosition({
  x: e.clientX,
  y: e.clientY,
});
```

<hr>

### 중첩 객체를 변경하지 않고 업데이트하는 방법

## 스프레드 구문으로 객체 복사 후 업테이트하는 방법

```js
import {useState} from 'react'

export default function Form() {
  const [person, setPerson] = useState({
    name: '홍길동',
    email: 'email@gmail.com',
    info: {
      age: "20"
      gender: "male",
      hobby: "coding",
    }
  })

  const handleNameChange = (e) => {
     setPerson({
      ...person,
      name: e.target.value
    });
  }

  const handleEmailChange = (e) => {
     setPerson({
      ...person,
      email: e.target.value
    });
  }

  const handleAgeChange = (e) => {
     setPerson({
      ...person,
      info: {
        ...person.info,
        age: e.target.value
      }
    });
  }

  const handleGenderChange = (e) => {
     setPerson({
      ...person,
      info: {
        ...person.info,
        gender: e.target.value
      }
    });
  }

  const handleHobbyChange = (e) => {
     setPerson({
      ...person,
      info: {
        ...person.info,
        hobby: e.target.value
      }
    });
  }

  return (
    <>
      <label>
        Name:
        <input value={person.name} onChange={handleNameChange} />
      </label>
      <label>
        Email:
        <input value={person.email} onChange={handleEmailChange} />
      </label>
       <label>
        Age:
        <input value={person.info.age} onChange={handleAgeChange} />
      </label>
      <label>
        Gender:
        <input value={person.info.gender} onChange={handleGenderChange} />
      </label>
      <label>
        Hobby:
        <input value={person.info.hobby} onChange={handleHobbyChange} />
      </label>
  )
}
```

## Immer로 객체 복사를 덜 반복적으로 만드는 간결한 업데이트 방법

Immer 라이브러리 사용하기

> npm install use-immer 설치
> import { useImmer } from 'use-immer' 추가하기

```js
import {useImmer} from 'use-immer'

export default function Form() {
  const [person, updatePerson] = useImmer({
    name: '홍길동',
    email: 'email@gmail.com',
    info: {
      age: "20"
      gender: "male",
      hobby: "coding",
    }
  })

  const handleNameChange = (e) => {
    updatePerson(draft => {
      draft.name = e.target.value;
    })
  }

  const handleEmailChange = (e) => {
     updatePerson(draft => {
      draft.email = e.target.value;
     });
  }

  const handleAgeChange = (e) => {
     updatePerson(draft => {
      draft.info.age => e.target.value;
     })
  }

  const handleGenderChange = (e) => {
     updatePerson(draft => {
      draft.info.gender => e.target.value;
     })
  }

  const handleHobbyChange = (e) => {
    updatePerson(draft => {
      draft.info.hobby =>  e.target.value;
    })
  }

  return (
    <>
      <label>
        Name:
        <input value={person.name} onChange={handleNameChange} />
      </label>
      <label>
        Email:
        <input value={person.email} onChange={handleEmailChange} />
      </label>
       <label>
        Age:
        <input value={person.info.age} onChange={handleAgeChange} />
      </label>
      <label>
        Gender:
        <input value={person.info.gender} onChange={handleGenderChange} />
      </label>
      <label>
        Hobby:
        <input value={person.info.hobby} onChange={handleHobbyChange} />
      </label>
  )
}
```
