---
layout: post
title:  "[css] Animation 과 keyframe"
subtitle:   ""
categories: css
comments: true
---


### Animation 이란?
애니메이션이란, 연속되는 이미지를 연결해서 자연스럽게 움직이는 것 처럼 보이게 만드는 기법을 통칭한다.

### CSS를 이용해서 애니메이션을 만드는 두 가지 방법
1. transition 속성 활용<br>
특정 이벤트를 기점으로 작동(hover 등)

2. animation 속성과 keyframe 활용<Br>
시작하기 위한 이벤트가 필요 없다. 그리고 애니메이션의 시작, 정지, 반복까지 제어가 가능하다.<br>
animation속성은 @keyframes로 애니메이션을 정의하고, 정의한 애니메이션을 불러와서 제어해주어야 힌다.

### CSS로 애니메이션을 만들 때…
1. transition으로 만들 수 있는 것은, transition 안에서 해결한다.
2. transition으로 만들 수 없는 애니메이션을 animation과 keyframes로 만든다.

<br>
<hr>
<br>

## @keyframes란?

CSS 애니메이션의 시작, 중간, 끝 등의 중간 상태를 정의한다.

<br>
☑️ keyframe 작성 방법<br>

```css
@keyframes 애니메이션이름 {
	from {
		left : 0;
	}
	to{
		left : 200px;
	}
}

/* from과 to 대신 진행도(%) 표기도 가능하다.*/
@keyframes 애니메이션이름{
	0% {
		left : 0;
	}
	50%{
		left : 200px;
	}
	100%{
		top : 200px;
		left :  200px;
	}
}
```

<br>

## animation 관련 속성들
animation-name: 어떠한 keyframes를 요소에 적용할 것인지 지정

animation-duration: 애니메이션을 한 번 재생하는데 걸리는 시간을 설정

animation-direction: 애니메이션 재생 방향을 정의(정방향/역방향)
* normal : 정방향으로 재생한다.
* reverse : 역방향으로 재생한다.
* alternate : 정방향으로 재생한다. (단, 반복시 정방향/역방향을 번갈아 재생한다.)
* alternate-reverse : 역방향으로 재생한다. (단, 반복시 역방향/정방향을 번갈아 재생한다.)


animation-iteration-count: 애니메이션 재생 횟수를 정의

animation-timing-function: 애니메이션 재생 패턴을 정의하며, transition-timing-function과 유사하다.

animation-delay: 애니메이션 시작을 얼마나 지연할 지 설정

animation 단축 속성: 애니메이션 카테고리에 속한 속성들을 단축 속성으로 모아서 지정 (작성 순서 유의)

<br>

```css
animation-name: moveRight
animation-duration: 0.4s
animation-direction: alternate | normal | reverse | alternate-reverse
animation-timing-function: linear | ease | ease-in | ease-out | ease-in-out
animation-iteration-count : infinite | 3
animation-timing-function : ease-in-out
animation-delay : 1s

/* 애니메이션 단축 속성 */
alternative: moveRight 0.4s ease-in-out 1s infinite alternative
```