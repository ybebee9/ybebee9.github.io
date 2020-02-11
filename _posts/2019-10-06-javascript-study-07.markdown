---
layout: post
title:  "7. 연산자"
date:   2019-10-06
categories: JavaScript
---  
  
## 연산자
  
### + 연산자  
두 연산자가 모두 숫자일 경우에만 더하기 연산이 수행되며,  
나머지는 문자열 연결 연산이 이뤄진다.  
  
**+연산자 예제**
```javascript

var add1 = 1 + 2;
var add2 = 'my' + 'string';
var add3 = 1 + 'string';
var add4 = 'string' + 2;

console.log(add1); // 3
console.log(add2); // mystring
console.log(add3); // 1string
console.log(add4); // string2

```
  
<br>
  
### typeof 연산자
  
**기본타입**
숫자       'number'  
문자열     'string'  
불린값     'boolean'  
null       'object'  
undefined  'undefined'  
<br>
**참조타입**
객체      'object'  
배열      'object'  
함수      'function'  
  
<br>
  
### == (동등) 연산자와 === (일치) 연산자
== 연산자 : 비교하려는 피연산자의 타입이 다를 경우에 타입 변환을 거친 다음 비교한다.  
=== 연산자 : 피연산자의 타입이 다를 경우에 타입을 변경하지 않고 비교한다.  
  
** == (동등) 연산자와 === (일치) 연산자의 차이점 **
``` javascript

console.log(1 == '1');	//true
console.log(1 === '1'); //false

```
  
<br>
  
### !! 연산자  
!! 연산자 : 피연산자를 boolean값으로 변환하는 것.  
  
**!! 연산자 활용을 통한 boolean값 변환**
```javascript

console.log(!!0);			    // false
console.log(!!1);			    // true
console.log(!!'string'); 	// true
console.log(!!'');			  // false
console.log(!!true);		  // true
console.log(!!false);		  // false
console.log(!!null);		  // false
console.log(!!undefined); // false
console.log(!!{});			  // true, 객체는 값이 비어있는 빈 객체라도 true로 변환되는것을 주의해야한다.
console.log(!![1,2,3]);   // true  

```
  
  
<br>
<br>
<br>
  
**Ref**  
---  
인사이드 자바스크립트
