---
layout: post
title:  "9. 함수 객체"
date:   2019-10-11
categories: JavaScript
---  
함수도 객체이므로, 일반 객체들처럼 프로퍼티들을 가질 수 있음.  
  
## 자바스크립트에서는 함수도 객체다  

**프로퍼티를 갖는 add()함수 예제 **
```javascript

// 함수 선언문 방식으로 add() 함수 정의. 함수 생성 코드는 함수 객체의 [[Code]] 내부 프로퍼티에 자동으로 저장됨.
function add(x,y) {
	return x+y;
}

// add()함수 객체에 result, status 프로퍼티를 동적으로 추가하고 값 저장
add.result = add(3,2);  
add.status = 'OK';  

// 객체명.프로퍼티명 으로 프로퍼티에 접근 
console.log(add.result); // 5
console.log(add.status); // 'OK'

```
  
<br>
  
## 자바스크립트에서는 함수는 값으로 취급된다  
자바스크립트에서 함수는 일급 객체이며, 일급 객체의 특성으로 함수형 프로그래밍이 가능하다.  
또한 함수는 일반 객체처럼 값(Value)으로 취급되기 때문에 함수를 변수나 객체, 배열 등에 값으로도 저장할 수 있으며 다른 함수의 인자로 전달한다거나 함수의 리턴값으로도 사용이 가능하다.  
  
**일급객체 특징**  
> ● 리터럴에 의해 생성  
> ● 변수나 배열의 요소, 객체의 프로퍼티 등에 할당 가능  
> ● 함수의 인자로 전달 가능  
> ● 함수의 리턴값으로 리턴 가능  
> ● 동적으로 프로퍼티를 생성 및 할당 가능  
  
<br>
  
### 변수나 프로퍼티의 값으로 할당  
**변수나 프로퍼티에 함수값을 할당하는 코드**  
```javascript

// 변수에 함수 할당
var foo = 100;
var bar = function () { return 100; };
console.log(bar()); // 100

// 프로퍼티에 함수 할당
var obj = {};
obj.baz = function () { return 200; };
console.log(obj.baz()); // 200

```  
  
<br>
  
### 함수 인자로 전달  
함수는 다른 함수의 인자로도 전달이 가능하다.  
**함수를 다른 함수의 인자로 넘긴 코드**  
```javascript

// 함수 표현식으로 foo()함수 생성
var foo = function(func){
	func(); // 인자로 받은 func()함수 호출. Function can be used as the argument 출력
};


// foo()함수 실행
foo(function() {
	console.log('Function can be used as the argument');
});

```  
  
<br>
  
### 리턴값으로 활용
함수는 다른 함수의 리턴값으로도 활용할 수 있다.  
```javascript

// 함수를 리턴하는 foo() 함수 정의
var foo = function() {
	return function() {
		console.log('this function is the return value');
	};
};

var bar = foo();
bar(); // this function is the return value

```  
  
<br>
  
## 함수 객체의 기본 프로퍼티  
자바스크립트에서는 함수 역시 객체다.  
하지만 일반 객체와는 다르게 추가로 함수 객체만의 표준 프로퍼티가 정의되어 있다.  
  
**add() 함수 객체 프로퍼티를 출력하는 코드**
```javascript

function add(x,y) {
	return x+y;
}

console.dir(add);

```  
  
ECMA5 스크립트 명세서에는 모든 함수가 length와 prototype 프로퍼티를 가져야 한다고 기술하고있다.  
  
<br>
  
### length 프로퍼티  
함수객체의 length 프로퍼티는 모든 함수가 가져야하는 표준 프로퍼티로써,  
함수가 정상적으로 실행될 때 기대되는 인자의 개수를 나타낸다.  
```javascript

function func0() {

};

function func1(x) {
	return x;
}

function func2(x,y) {
	return x + y;
}

function func3(x,y,z) {
	return x + y + z;
}

console.log('func0.length-' + func0.length); // func0.length- 0
console.log('func1.length-' + func1.length); // func1.length- 1
console.log('func2.length-' + func2.length); // func2.length- 2
console.log('func3.length-' + func3.length); // func3.length- 3

```  
  
**함수객체의 length 프로퍼티는 함수를 작성할 때 정의한 인자 개수를 나타내고 있음을 확인할 수 있다.**  
  
<br>
  
### prototype 프로퍼티  
모든 함수는 객체로써 prototype 프로퍼티를 가지고 있다.  
여기서 말하는 prototype 프로퍼티는 모든 객체의 부모를 나타내는 내부 프로퍼티인 [[Prototype]] 프로퍼티를 말하는게 아니므로 혼동하지 말자.  

함수 객체의 prototype 프로퍼티는 함수가 생성될 때 만들어지며 constructor 프로퍼티 하나만 있는 객체(프로토타입 객체)를 가리킨다.  
그리고 prototype 프로퍼티가 가리키는 프로토타입 객체의 유일한 constructor 프로퍼티는 자신과 연결된 함수(함수 객체)를 가리킨다.  
즉, 함수객체의 prototype 프로퍼티와 프로토타입객체의 constructor 프로퍼티는 서로를 참조한다.  
  
**함수 객체와 프로토타입 객체와의 관계를 보여주는 코드**  
```javascript

// MyFunction() 함수 정의
function myFunction(){
	return true;
}

console.dir(myFunction.prototype); // 프로토타입 객체 출력됨. constructor 프로퍼티가 myFunction 함수 객체 가리킴
console.dir(myFunction.prototype.constructor); // myFunction객체 출력됨. prototype 프로퍼티가 constructor 객체 가리킴 

```  
<br>
<br>
<br>
  
**Ref**  
---  
인사이드 자바스크립트
