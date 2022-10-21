---
layout: post
title:  "[JavaScript] web Storage 사용하기"
subtitle:   ""
categories: js
comments: true
---

## web Storage
웹 브라우저에서 제공하는 데이터 저장소<br>
seesionStorage 와 localStorage 를 활용할 수 있다.

<br>

### sessionStorage & localStorage 공통점:
- 로컬 환경에 데이터 저장
- key-value 형태로 저장
- 문자열 형태로 데이터 저장


### sessionStorage & localStorage 차이점:

|sessionStorage|localStorage|
|-|-|
|세션 단위로 데이터가 저장 | 도메인 단위로 데이터가 저장|
|브라우저, 탭을 종료하면 영구 삭제 |브라우저, pc를 종료해도 존재 |

*** Session:
사용자가 브라우저를 통해 페이지에 접속한 시점부터, 해당 접속을 종료하는 시점까지를 의미하는 단위

*** Domain:
url의 프로토콜(http://) 바로 뒷부분에 따라오는 문자를 통해 도메인(localhost)을 확인할 수 있다.
"http://localhost:5500/user/login"
"http://localhost:5500/post"
=> localhost라는 공통된 도메인, 서로 다른 path(/user/login, /post)

<br>

### localStorage 사용하기
* localStorage.setItem()<br>
	데이터를 저장할 때는 localStorage에 내장되어 있는 setItem이라는 메서드 를 사용<br>
소괄호 안에 저장할 데이터를 ("key", "value")형태로 넣어준다.

	localStorage.setItem('data-key', 'data-value')

<br>

* localStorage.getItem()<br>
localStorage에 저장된 데이터를 꺼낼 때 사용.

	localStorage.getItem('data-key')

<br>

* localStorage.removeItem()<br>
localStorage에 저장된 데이터를 삭제할 때 사용.


