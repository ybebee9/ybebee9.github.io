---
layout: post
title:  "4. 프로토타입"
date:   2019-10-04
categories: JavaScript
---  
## 프로토타입  
자바스크립트의 모든 객체는 자신의 부모 역할을 하는 객체와 연결되어있음.  
객체 지향의 상속 개념과 같이 부모 객체의 프로퍼티를 마치 자신의 것처럼 쓸 수 있는것 같은 특징이 있음.  
자바스크립트에서는 이러한 부모객체를 프로토타입 객체 라고 부른다.  

**객체 생성 및 출력**  
```javascript

var foo = {
	name : 'foo',
	age : 30
};

// foo 객체에는 toString() 메서드가 없으므로 에러가 발생해야함. 하지만 foo 객체의 프로토타입에 toString()메서드가 이미 정의되어있으므로 오류없이 정상적으로 출력됨.
foo.toString();

console.dir(foo);

```

![img01]({{ site.baseurl }}/images/post/javascript/prototype.png)<br>
__proto__ 프로퍼티에서 toString()메서드 존재 확인  
  
<br>
<br>
  
ECMAScript 명세서에는 자바스크립트의 모든 객체는 자신의 프로토타입을 가리키는 [[Prototype]]라는 숨겨진 프로퍼티를 가진다고 설명하고있음.  
<br>
객체 리터럴 방식으로 생성된 객체의 경우 Object.prototype 객체가 프로토타입 객체가 된다.  
foo 객체의 __proto__ 프로퍼티가 가리키는 객체가 바로 Object.prototype 이며,  
toString(), valueOf() 등과 같은 모든 객체에서 호출 가능한 자바스크립트 기본 내장 메서드가 포함되어 있다.  
자신의 프로토타입인 부모 객체에 포함된 다양한 메서드를 마치 자신의 프로퍼티인것처럼 상속받아 사용할 수 있다.  
  
또한 객체를 생성할 때 결정된 프로토타입 객체를 임의의 다른 객체로 변경하는것도 가능.  
즉, 부모객체를 동적으로 바꿀 수 있음.  
  
  
  
<br>
<br>
<br>
![img01]({{ site.baseurl }}/images/post/javascript/InsideJavascript.PNG)<br>
<br>
본 포스팅은 인사이드 자바스크립트 책을 공부한 내용을 바탕으로 작성하였습니다.<br>
<br>
<br>
<br>