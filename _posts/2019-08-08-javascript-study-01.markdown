---
layout: post
title:  "1. 자바스크립트 기본타입"
date:   2019-08-12
categories: JavaScript
---  
<br>

## 자바스크립트 기본타입

자바스크립트의 기본타입은 숫자, 문자열, boolean, null, undefined 타입이 있다. 

이들 타입의 특징은 그 자체가 하나의 값을 나타낸다는 것이다. 

자바스크립트는  변수를 선언할 때 타입을 미리 정하지 않고, var라는 한가지 키워드로만 변수를 선언한다. 

이렇게 선언된 변수에는 어떤 타입의 데이터라도 저장하는것이 가능하다.

따라서 자바스크립트에서는 변수에 어떤 형태의 데이터를 저장하느냐에 따라 해당 타입의 변수가 결정된다. 



```javascript
//숫자타입
var intNum = 10;
var floatNum = 0.1;

//문자열타입
var singleQuoteStr = 'single quote string';
var doubleQuoteStr = "double quote string";
var singleChar = 'a';

//boolean타입
var boolVar = true;

//undefined타입
var emptyVar;

//null타입
var nullVar = null;

console.log(typeof intNum, typeof floatNum, typeof singleQuoteStr, typeof doubleQuoteStr, typeof singleChar, typeof emptyVar, typeof nullVar);
```



```javascript
// 출력결과
number number string string boolean object undefined
```



### 1.숫자

- 자바스크립트는 하나의 숫자형(number)만 존재한다.
- 자바스크립트에서 모든 숫자를 64비트 부동 소수점 형태로 저장한다.
- 자바스크립트에서는 정수형이 따로 없고, 모든 숫자를 실수로 처리한다(나눗셈 연산에 주의).
- var 키워드로 선언된 자바스크립트 변수에 정수나 실수 구분없이 그 값을 바로 저장할 수 있다.



```javascript
var num = 5/2;

console.log(num);
console.log(Math.floor(num));
```



```javascript
// 출력결과
2.5
2
```



### 2.문자열

- 문자열은 작은 따옴표(')나 큰 따옴표(")로 생성한다.
- 문자열은 문자 배열처럼 인덱스를 이용해서 접근할 수 있다.
- 자바스크립트에서 한번 생성된 문자열은 읽기만 가능하지, 수정은 불가능하다.

```javascript
// str 문자열 생성
var str = 'test';
console.log(str[0],str[1],str[2],str[3]);

// 문자열의 첫 글자를 대문자로 변경
str[0]='T';
console.log(str);
```



```javascript
// 출력결과

```





