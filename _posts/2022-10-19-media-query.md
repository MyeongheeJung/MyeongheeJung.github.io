---
layout: post
title:  "[css] Media Query 사용하기"
subtitle:   ""
categories: css
comments: true
---


## 반응형 웹이란?
다양한 디바이스에서 접속했을 때 기기의 Viewport 규격에 반응하여 레이아웃이 자동으로 변경되는 웹페이지 를 뜻한다.

<br>

## Viewport란?
웹 브라우저를 통해 웹페이지에 접속했을 때, 주소창이나 탭 등을 제외하고 실제 웹페이지의 컨텐츠가 차지하는 영역을 의미한다.이 Viewport는 Device의 종류에 따라 다르다.(크롬 개발자도구에서 기기별 Viewport를 확인할 수 있다.)

<br>

## 미디어 쿼리란?
Viewport의 너비에 따라 웹사이트의 스타일 시트를 수정할 수 있게 해주는 CSS의 기능이다.이 때, Viewport 너비 이외에도 단말기의 종류, 해상도 등을 기준으로 설정할 수 있다.

* @media : 미디어 쿼리를 사용한다는 의미

* screen : 미디어 타입 지정. 이 페이지가 screen에 노출되었을 때 (중괄호) 안에 입력한 스타일 시트를 적용한다는 의미

* max-width: 00px : viewport 너비가 00px 이하일 경우 해당 스타일 시트를 적용한다는 의미

* min-width: 00px : viewport 너비가 00px 이상일 경우 해당 스타일 시트를 적용한다는 의미

* and: screen, max-width 등 여러가지 미디어 쿼리 조건을 연결시켜 준다. and로 연결한 모든 조건을 만족하는 경우에 해당 스타일 시트를 적용합니다.

```css
@media screen and (max-width: 767px) {
	/* 스크린의 너비가 767px 이하일 경우 적용시킬 스타일 시트를 적는다. */
}

@media screen and (min-width:768px) and (max-width:1023px) {
	/* 스크린의 너비가 768px ~ 1023px 사이일 경우 적용시킬 스타일 시트를 적는다. */
}

@media screen and (min-width: 1024px) {
	/* 스크린의 너비가 1024px 이상일 경우 적용시킬 스타일 시트를 적는다. */
}
```

<br>

## breakPoint란?
breakPoint란 반응형 웹페이지의 작업 기준이 되는 중단점을 의미한다.<br>간단하게 말해서, PC / Tablet / Mobile의 기준이 되는 규격 분기이다.


[ 가장 일반적으로 사용되는 breakPoint ]
	

| 크기 | breakPoint |
|:----------|:----------|
| Mobile    | 0 ~ 767px    |
| Tablet    | 768px ~ 1923px   |
| PC    | 1024px ~ 1439px    |
| PC Large    | 1440px ~    |


하지만, 이건 어디까지나 가장 일반적인 규격일 뿐이고, 상황에 따라 더 자세하게 나누는 것도 가능하다.
breakPoint를 많이 나누면 더 좋은 서비스를 만들 수 있겠지만, 그만큼 개발하는 시간이 늘어나고 인건비가 증가한다.그래서 보통 웹 서비스를 기획하는 단계에서 프로젝트의 예산과 기간을 고려하여 breakPoint를 몇 단계로 나눌 것인지 결정하게 된다.

<br>

## 반응형 웹에 자주 쓰이는 속성
max-width: 요소의 최대 가로 크기을 지정


max-height: 요소의 최대 세로 크기을 지정

min-width: 요소의 최소 가로 크기를 지정

min-height: 요소의 최소 세로 크기를 지정

max(): 소괄호 안에 입력된 값 중 제일 높은 값을 속성값으로 출력하는 함수. 소괄호 안에는 여러 개의 값을 콤마로 연결해 입력해줄 수 있다.

min(): 소괄호 안에 입력된 값 중 제일 낮은 값을 속성값으로 출력하는 함수. 소괄호 안에는 여러 개의 값을 콤마로 연결해 입력해줄 수 있다.
```css
max-width : 1240px;
max-height: 100vh
min-width : 720px;
min-height : 30%;
height : max(320px, 20%)
width : min(1240px, 100%)
```
