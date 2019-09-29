---
layout: post
title:  "2. 자바스크립트 참조타입(객체타입)"
date:   2019-09-30
categories: JavaScript
---  
## 자바스크립트 참조타입(객체타입)  
자바스크립트에서 숫자, 문자열, 불린값, null, undefined 같은 기본타입을 제외한 모든 값은 객체다.  
따라서 배열, 함수, 정규표현식 등도 모두 자바스크립트 객체로 표현됨.  
  
자바스크립트에서 객체는 단순히 '이름(key):값(value)' 형태의 프로퍼티들을 저장하는 컨테이너로서 Hash라는 자료구조와 굉장히 유사하다.  
참조타입 객체는 여러개의 프로퍼티들을 포함할 수 있다.  
  
이러한 프로퍼티의 성질에 따라 객체의 프로퍼티는 함수로 포함할 수 있으며, 자바스크립트에서는 이러한 프로퍼티를 메서드라고 부른다.  
  

### 객체생성  
자바에서 객체를 생성하는 방법은 크게 3가지이다.  
- 기본 제공 Object() 객체 생성자 함수를 이용하는 방법  
- 객체 리터럴을 이용하는 방법  
- 생성자 함수를 이용하는 방법  
  
<br>
  
### Object() 생성자 함수 이용  
Object() 생성자 함수를 통한 객체생성  
```javascript
// Object를 이용해서 foo 빈 객체 생성
var foo = new Object();

// foo 객체 프로퍼티 생성
foo.name = 'foo';
foo.age = 30;
foo.gender - 'male';

console.log(typeof foo); // (출력값) object
console.log(foo);  // (출력값) {name:'foo', age:30, gender:'male'}
```   
  
<br>
  
### 객체 리터럴 방식 이용  
리터럴이란 용어의 의미는 표기법이다.  
객체 리터럴 = 객체를 생성하는 표기법  
객체 리터럴 방식은 간단한 표기법만으로도 객체를 생성할 수 있는 자바스크립트의 강력한 문법  
```javascript
// 객체 리터럴 방식으로 foo 객체 생성
var foo = {
	name : 'foo',
	age : 30,
	gender : 'male'
};

console.log(typeof foo); // (출력값) object
console.log(foo); // (출력값) {name: 'foo', age: '30', gender: 'male'}
```
  
<br>
  
### 생성자 함수 이용  
자바스크립트의 경우 함수를 통해서도 객체를 생성할 수 있다.  
이렇게 객체를 생성하는 함수를 생성자 함수라고 한다.  
생성자 함수는 별도로 따로 포스팅 할 예정..  
  
<br>
  
### 객체 프로퍼티 읽기/쓰기/갱신  
객체는 새로운값을 가진 프로퍼티를 생성하고, 생성된 프로퍼티에 접근해서 해당 값을 읽거나 또는 원하는 값으로 프로퍼티의 값을 갱신할 수 있음.  
객체의 프로퍼티에 접근하려면 두가지 방법을 사용한다.  
- 대괄호([]) 표기법
- 마침표(.) 표기법
  
```javascript
// 객체 리터럴 방식을 통한 foo 객체 생성  
var foo = {
	name : 'foo',
	major : 'computer science'
};


// 객체 프로퍼티 읽기
console.log(foo.name);		// (출력값) foo
console.log(foo['name'])	// (출력값) foo
console.log(foo.nickname)	// (출력값) undefined


// 객체 프로퍼티 갱신
foo.major = 'electronics engineering';
console.log(foo.major);		// (출력값) electronics engineering
console.log(foo['major']);	// (출력값) electronics engineering


// 객체 프로퍼티 동적 생성
foo.age = 30;
console.log(foo.age);	// (출력값) 30


// 대괄호 표기법만을 사용해야 할 경우 
foo['full-name'] - 'foo bar';
console.log(foo['full-name']);		// (출력값) foo bar
console.log(foo.full-name);			// (출력값) NaN
console.log(foo.full);				// (출력값) undefined
console.log(name);					// (출력값) undefined


```
**대괄호 표기법만을 사용해아하는 경우**  
접근하려는 프로퍼티가 표현식이거나 예약어일 경우다.  
이때 대괄호 표기법만을 이용해서 접근해야한다. 'full-name'은  '-'연산자가 있는 표현식이다.  
이 경우에는 대괄호표기법을 이용해서 foo['full-name'] 형태로 프로퍼티에 접근해야한다.  
foo.full-name 에서 NaN이 출력된 이유는 full - name 으로 계산하는 표현식으로 취급했기 때문이다.  
NaN : Not a Number의 약자로 수치연산을 해서 정상적인 값을 얻지 못할 때 출력되는 값이다.  
  
<br>
  
### for in 문과 객체 프로퍼티 출력  
for in 문을 사용하면, 객체에 포함된 모든 프로퍼티에 대해 루프를 수행할 수 있다.
**for in문을 통한 객체 프로퍼티 출력**
```javascript
// 객체 리터럴을 통한 foo 객체 생성
var foo = {
	name : 'foo',
	age : 30,
	major : 'computer science'
};


// for in 문을 이용한 객체 프로퍼티 출력 
var prop;
for (prop in foo){
	console.log(prop, foo[prop]);
}
``` 

```javascript
// 출력결과
name 'foo'
age 30
major 'computer science'
```
  
<br>
  
### 객체 프로퍼티 삭제  
자바스크립트에서는 객체의 프로퍼티를 delete 연산자를 이용해 즉시 삭제할 수 있다.  
delete 연산자는 객체의 프로퍼티를 삭제할 뿐, 객체 자체를 삭제하지는 못한다.  
```javascript

// 객체 리터럴을 통한 foo 객체 생성
var foo = {
	name : 'foo',
	nickname : 'babo'
};

console.log(foo.nickname);		// (출력값) babo
delete foo.nickname;
console.log(foo.nickname);		// (출력값) undefined

delete foo;
console.log(foo.name);			// (출력값) foo
```
  
  
  
<br>
<br>
<br>
![img01]({{ site.baseurl }}/images/post/javascript/InsideJavascript.PNG)<br>
<br>
본 포스팅은 인사이드 자바스크립트 책을 공부한 내용을 바탕으로 작성하였습니다.<br>
<br>
<br>
<br>