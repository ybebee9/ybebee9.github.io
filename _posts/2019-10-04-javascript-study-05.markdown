---
layout: post
title:  "5. 배열"
date:   2019-10-04
categories: JavaScript
---  
## 배열  
자바스크립트의 배열은 객체의 특별한 형태임.  
굳이 크기를 지정하지 않아도 되며, 어떤 위치에 어느 타입의 데이터를 저장하더라도 에러가 발생하지 않는다.  
  
  
### 배열 리터럴  
배열리터럴은 자바스크립트에서 새로운 배열을 만드는데 사용하는 표기법.  
배열 리터럴은 대괄호([])를 사용한다.  
  
**배열 리터럴을 통한 배열 생성**
```javascript

// 배열 리터럴을 통한 5개 원소를 가진 배열 생성
var colorArr = ['orange','yellow','blue','green','red'];

console.log(colorArr[0]); // 출력값 orange

console.log(colorArr[1]); // 출력값 yellow

console.log(colorArr[4]); // 출력값 red

```
  
<br>
<br>
  
### 배열의 요소 생성
객체가 동적으로 프로퍼티를 추가할 수 있듯이, 배열도 동적으로 배열 원소를 추가할 수 있다.  
특히, 자바스크립트의 경우는 값을 순차적으로 넣을 필요 없이 아무 인덱스 위치나 값을 동적으로 추가할 수 있다.  
  
**배열요소의 동적 생성**
```javascript

// 빈배열 생성
var emptyArr = [];

console.log(emptyArr[0]); // undefined. 값이 없는 원소에 접근할 경우 undefined 출력 

// 배열요소 동적 생성. 배열 내에 추가하고자하는 아무 위치에나 값을 저장하면 된다. 
/* 배열의 요소는 숫자, 문자열같은 기본 타입의 값들을 포함해서 객체나 함수 배열 등과 같이 자바스크립트의 모든 데이터 타입의 값을 포함할 수 있다. */
emptyArr[0] = 100;
emptyArr[3] = 'eight';
emptyArr[7] = true;

console.log(emptyArr); //[100,undefined x 2, "string", undefined x 3, true]

// 자바스크립트가 배열의 크기를 현재 배열의 인덱스 중 가장 큰값을 기준으로 정한다. 그래서 3개요소만 동적으로 추가했지만 배열의 길이는 8. 0~7까지.
console.log(emptyArr.length); // 8

```
  
<br>
<br>
  
### 배열의 length 프로퍼티
length 프로퍼티는 배열의 원소 개수를 나타내지만, 실제로 배열에 존재하는 원소 개수와 일치하는것은 아니다.  
length 프로퍼티는 배열 내에 가장 큰 인덱스에 1을 더한 값이다.  
  
**배열의 length 프로퍼티 변경**
```javascript

var arr = [];
console.log(arr.length); // 0

arr[0] = 0; // arr.length = 1
arr[1] = 1; // arr.length = 2
arr[2] = 2; // arr.length = 3
arr[100] = 100; 
console.log(arr.length); // arr.length = 101

```
  
  
  
**배열 length 프로퍼티의 명시적 변경**  
```javascript

var arr = [0,1,2];
console.log(arr.length);	// 3

arr.length = 5;
console.log(arr);		// [0,1,2, undefined x 2]

arr.length = 2;
console.log(arr);		// [0,1]
console.log(arr[2]);	// undefined
 
```
  
  
  
### 배열 표준 메서드와 length 프로퍼티  
자바스크립트는 배열에서 사용 가능한 다양한 표준 메서드를 제공한다.  
push() 메서드는 인수로 넘어온 항목을 배열의 끝에 추가하는 자바스크립트 표준 배열 메서드다.  
  
**push()메서드와 length 프로퍼티**
```javascript

// arr 배열 생성
var arr = ['zero','one','two'];

// push() 메서드 호출
arr.push('three');
console.log(arr); // ['zero','one','two','three']


arr.length = 5; 
arr.push('four');
console.log(arr); // ['zero','one','two','three','undefined','four']


```
  
  
  
### 배열과 객체  
자바스크립트에서는 배열 역시 객체지만, 일반객체와는 약간 차이가 있다.  
  
**배열과 객체의 유사점 차이점**
```javascript

// colorsArray 배열
var colorsArray = ['orange', 'yellow', 'green'];

console.log(colorsArray[0]); // orange
console.log(colorsArray[1]); // yellow
console.log(colorsArray[2]); // green


// colorsObj 객체
var colorsObj = {
	'0' : 'orange',
	'1' : 'yellow',
	'2' : 'green'
};

/*	객체의 프로퍼티에 접근할때 대괄호 안에 프로퍼티의 속성을 문자열 형태로 적어야 한다. 
	colorsObj['0']의 형태로 기입하는것이 맞지만, 자바스크립트 엔진이 [] 연산자 내에 숫자가 사용될 경우 
	해당 숫자를 자동으로 문자열 형태로 바꿔줘서 결과가 정상적으로 출력된다. */ 
console.log(colorsObj[0]); // orange
console.log(colorsObj[1]); // yellow
console.log(colorsObj[2]); // green

// type of 연산자 비교
console.log(typeof colorsArray); 	// object(not array)
console.log(typeof colorsObj);		// object

// length 프로퍼티
/*	배열과 객체는 부모인 프로토타입 객체가 서로 다르다.
	배열의 경우 Array.prototype 객체가 부모 객체인 프로토타입이다.
	객체의 경우 Object.prototype 객체가 부모 객체인 프로토타입이다.
	Array.prototype은 배열에서 사용할 push(), pop() 같은 표준 메서드를 포함하고 있다.
	그리고 Array.prototype 객체의 프로토타입은 Object.prototype 객체다.
	배열은 Array.prototype에 포함된 배열 표준 메서드와 Object.prototype의 표준 메서드들을 모두 사용 할 수 있다. 
 */
console.log(colorsArray.length);	// 3
console.log(colorsObj.length);		// undefined

// 배열 표준 메서드 
colorsArray.push('red'); 	// ['orange','yellow','green','red']
colorsObj.push('red');		// Uncaught TypeError: Object #<Object> has no method 'push'

``` 
  
<br>
<br>
  
**배열의 프로토타입과 객체의 프로토타입 비교**
```javascript

// 배열 리터럴을 통한 빈 배열 생성
var emptyArray = [];

// 객체 리터럴을 통한 빈 객체 생성
var emptyObj = [];


console.dir(emptyArray.__proto__); // 배열의 프로토타입(Array.prototype) 출력


console.dir(emptyObj.__proto__); // 객체의 프로토타입(Object.prototype) 출력


```

![img01]({{ site.baseurl }}/images/post/javascript/prototype2.PNG)<br>
Array.prototype 객체내에 push() 메서드를 비롯한 다양한 자바스크립트의 표준 배열 메서드가 있다는 것을 확인 할 수 있다.  
Array.prototype의 __proto__ 프로퍼티가 있다는것을 확인할 수 있으며, 이 값은 Object.prototype을 가리킨다.  
Object.prototype은 일반 객체이므로 프로토타입인 __proto__ 프로퍼티가 Object.prototype을 가리킨다.  
  
<br>
<br>
  
### 배열의 프로퍼티 동적 생성  
배열도 자바스크립트 객체이므로 동적으로 프로퍼티를 추가할 수 있다.  
  
**배열의 동적 프로퍼티 생성**
```javascript

// 배열 생성
var arr = ['zero','one','two'];
console.log(arr.length); // 3

// 프로퍼티 동적 추가
/*	배열의 동적 프로퍼티가 추가 될 경우는 배열의 length값이 바뀌지 않는다.
	즉, 배열의 length 프로퍼티는 배열 원소의 가장 큰 인덱스가 변했을 경우만 변경된다. */
arr.color = 'blue';
arr.name = 'number_array';

console.log(arr.length); // 3

// 배열 원소 추가
arr[3] = 'red';
console.log(arr.length); // 4

// 배열 객체 출력
console.dir(arr);

```
  
![img01]({{ site.baseurl }}/images/post/javascript/prototype3.PNG)<br>
  
<br>
  
### 배열의 프로퍼티 열거  
객체는 for in 문으로 프로퍼티를 열거한다.  
배열도 객체이므로 for in문을 사용해서 배열 내의 모든 프로퍼티를 열거할 수 있지만,
불필요한 프로퍼티가 출력될 수 있으므로 되도록 for문 사용하는것이 좋다. 
```javascript

for(var prop in arr){
	console.log(prop, arr[prop]);
}

for(var i=0; i<arr.length; i++){
	console.log(i, arr[i]);
}


// 출력결과 

0 zero

1 one

2 two

3 red

color blue

name number_array


0 "zero"

1 "one"

2 "two"

3 "red" 

```
  
<br>
<br>
  
### 배열 요소 삭제 
배열도 객체이므로 배열 요소나 프로퍼티를 삭제하는데 delete 연산자 사용 가능.
  
**delete 연산자를 이용한 배열 프로퍼티 삭제**
```javascript

var arr = ['zero','one','two','three'];

// delete 연산자는 해당 요소의 값을 undefined로 설정할 뿐 원소 자체를 삭제하지는 않는다.
delete arr[2];

console.log(arr); // ['zero','one',undefined,'three']
console.log(arr.length); // 4

```
  
<br>
  

**splice() 메서드를 이용한 배열 프로퍼티 삭제**
```javascript

var arr = ['zero','one','two','three'];

arr.splice(2,1);	// 2번째 요소를 시작점으로 1개의 원소를 삭제한다.

console.log(arr);	// ["zero","one","three"]
console.log(arr.length)	// 3

```
  
<br>
<br>
  
### Array() 생성자 함수  
배열은 일반적으로 배열 리터럴로 생성하지만,  
배열 리터럴도 결국 자바스크립트 기본 제공 Array() 생성자 함수로 배열을 생성하는 과정을 단순화시킨것이다.  
Array() 생성자 함수는 호출할 때 인자 개수에 따라 동작이 다르다.  
(1) 호출할 때 인자가 1개이고, 숫자일 경우 : 호출된 인자를 length로 갖는 빈 배열 생성
(2) 그 외의 경우 : 호출된 인자를 요소로 갖는 배열 생성  
  
**Array() 생성자 함수를 통한 배열 생성**
```javascript

// 호출할 때 인자가 1개이고, 숫자일 경우 : 호출된 인자를 length로 갖는 빈 배열 생성
var foo = new Array(3);
console.log(foo);	// [undefined,undefined,undefined]
console.log(foo.length) // 3

// 그 외의 경우 : 호출된 인자를 요소로 갖는 배열 생성 
var bar = new Array(1,2,3);
console.log(bar); // [1,2,3]
console.log(bar.length); // 3

```
  
<br>
<br>
  
### 유사 배열 객체  
자바스크립트에서는 length 프로퍼티를 가진 객체를 유사 배열 객체라고 부른다.  
이런 유사 배열 객체의 가장 큰 특징은, 객체임에도 불구하고 자바스크립트의 표준 배열 메서드를 사용하다는 게 가능하다는 것이다.  
  
**유사 배열 객체의 배열 메서드 호출**
```javascript

var arr = ['bar'];
var obj = {
	name : 'foo',
	length : 1
};


arr.push('baz');
console.log(arr); // ['bar','baz']

obj.push('baz'); // error 

``` 
  
<br>
  
**유사 배열 객체에서 apply()를 활용한 배열 메서드 호출**
```javascript

var arr = ['bar'];
var obj = {name : 'foo', length : 1};

arr.push('baz');
console.log(arr); // ['bar','baz']

// apply() 메서드를 사용하면 객체지만 표준 배열 메서드를 활용하는 것이 가능
Array.prototype.push.apply(obj,['baz']);
console.log(obj); // {'1':'baz', name:'foo', length:2}

```
  
**유사 배열 객체도 배열 메서드를 사용하는 것이 가능하다.**

  
<br>
<br>
<br>
  
**Ref**  
---  
인사이드 자바스크립트
