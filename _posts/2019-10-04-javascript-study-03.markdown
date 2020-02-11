---
layout: post
title:  "3. 참조타입의 특성"
date:   2019-10-04
categories: JavaScript
---  
## 참조 타입의 특성  
자바스크립트에서 기본타입인 문자, 숫자, 문자열, boolean값, null, undefined 5가지를 제외한 모든 값은 객체(배열, 함수도 객체로 취급)다.  
자바스크립트 참조타입 = 객체  
**Why?** 객체의 모든 연산이 실제 값이 아닌 참조값으로 처리되기 때문.  
<br>
**동일한 객체를 참조하는 두 변수 objA와 objB**
```javascript

// 객체 리터럴 방식으로 objA 객체 생성
var objA = {
	val : 40
};

// objB에 objA가 가르키는 참조값 저장됨
var objB = objA;

console.log(objA.val);
console.log(objB.val);

// objB가 가리키는 객체의 val값을 50으로 갱신
objB.val = 50;

// objA와 objB가 동일한 객체를 참조하고 있으므로 objA.val 값이 50으로 변경된것 확인
console.log(objA.val); // 50
console.log(objB.val); // 50

```
  
<br>
<br>
  
### 객체비교  
동등 연산자(==)를 사용하여 두 객체를 비교할 때도 참조값을 비교한다는 것에 주의해야함.  
**기본 타입과 참조 타입의 비교 연산**
```javascript

var a = 100;
var b = 100;

var objA = {value : 100};
var objB = {value : 100};
var objC = objB;


// 기본타입의 경우 값을 비교
console.log(a == b);  		// true

// 객체와 같은 참조타입의 경우 참조값이 같아야 true 
console.log(objA == objB);  // false

// 동일한 객체 참조하기 때문에 true
console.log(objB == objC);  // true

```
  
<br>
<br>
  
### 참조에 의한 함수 호출 방식  
**기본타입 호출 방식** : 값에 의한 호출(Call By Value) 방식. 함수를 호출할 때 인자로 기본 타입의 값을 넘길 경우, 호출된 함수의 매개변수로 복사된 값이 전달됨. 함수 내부에서 매개변수를 이용해 값을 변경해도, 실제로 호출된 변수의 값이 변경되지는 않음.  
  
**참조타입 호출 방식** : 참조에 의한 호출(Call By Reference) 방식. 함수를 호출할 때 인자로 참조 타입인 객체를 전달할 경우, 객체의 프로퍼티값이 함수의 매개변수로 복사되지 않고, 인자로 넘긴 객체의 참조값이 그대로 함수 내부로 전달됨. 함수 내부에서 참조값을 이용해서 인자로 넘긴 실제 객체의 값을 변경할 수 있다.  
  
**Call by Value와 Call by Reference 차이**
```javascript

var a = 100;
var objA = { value : 100 };

function changeArg(num, obj){

	num = 200;
	obj.val = 200;

	console.log(num); // 200
	console.log(obj); // 200

}

changeArg(a,objA);

console.log(a); // 100
console.log(objA); // 200

```
  
  
  
<br>
<br>
<br>
  
**Ref**  
---  
인사이드 자바스크립트

