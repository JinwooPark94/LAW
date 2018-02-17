# 함수(Function) - 2

## 5. 함수의 다양한 형태

### 5-1. 즉시호출함수표현식 (IIFE,  Immediately Invoke Function Expression)

함수 정의와 동시에 즉시 호출하는데 딱 한번 호출함

> 실행이 필요한 초기화 처리등에 사용 가능

```javascript
// 기명 즉시호출함수
(function nameFunction() {

}());

// 익명방법
(function () {

}());
```

### 5-2. 내부 함수 (Inner function)

함수 내부에 있는 함수를 내부함수

```javascript
//부모함수
function parent() {
  // 내부함수
  function child(){
  }
}
```

- 자식은 부모의 변수에 접근이 가능하지만 부모는 자식의 변수에 접근 불가능함
- 안의 내부함수는 부모함수의 외부에서 접근할 수 없음

### 5-3. 콜백 함수 (Callback function)

![참고 : http://poiemaweb.com/js-function - callback function](http://poiemaweb.com/img/callback.png)

특정한 이벤트가 발생할때 호출되는 함수

> 나중에 호출하는 함수

```javascript
function laterCall() {
  var name = 'Park';

  // 0.03초 후에 함수 실행
  setTimeout(function () {
    console.log('My name is ' + name);
  }, 300);
}

doSomething(); // My name is Park 이라고 출력됨
```

### 5-4. 재귀함수 (Recursion Function)

자기 자신을 재호출 하는 함수

```javascript
// 가장 이해하기 factorial의 예
// factorial이란 계승의 계산이며, 만약 3의 값이 들어오면 1 * 2 * 3을 곱한 계산인 6이 나옴
function factorial(num)
{
    // 0 보다 작은 경우 -1 반환
    if (num < 0) {
        return -1;
    }
    // 0과 같은 경우 1을 반환
    else if (num == 0) {
        return 1;
    }
    var tmp = num;
    while (num-- > 2) {
        tmp *= num;
    }
    return tmp;
}
console.log(factorial(8)); // 40320
```

## 6. 함수 객체의 속성

### 6-1. arguments 속성

함수 호출시 함수 값에 arguments를 자동 생성하고 인수들의 정보를 담고 있는 순회가능한 유사배열 객체

> 유사배열 객체(array-like object) : 배열처럼 움직이는 객체

```javascript
function multiply(x, y) {

  // 방어코드 넣기

  console.log(arguments);
  return x * y;
}

multiply();        // {}
multiply(1);       // { '0': 1 }
multiply(1, 2);    // { '0': 1, '1': 2 }
multiply(1, 2, 3); // { '0': 1, '1': 2, '2': 3 }
```

### 6-2. caller 속성

자신이 호출한 함수를 의미

```javascript
function restaurant(personFunc){
  var table = personFunc();
  return desk;
}
function person(){
  return person.caller;
}

console.log(restaurant(person)); // function restaurant의 속성을 가지고 있음
```

### 6-3. length 속성

함수에서 매개변수의 개수를 의미

```javascript
function person( name, gender, country ){}
console.log(person.length); // 3
```

### 6-4. name 속성

기명 함수 또는 익명 함수에 사용되며

```javascript
function person( name, gender, country ){}
console.log(person.name); // 여기서의 person name은 함수 function의 이름인 person이 출력됨
```

### 6-5. ______proto__ 속성

- 함수 객체를 포함한 모든 객체가 가지고 있는 프로퍼티
- 자신의 부모역할을 할 프로포타입 객체를 가르킴
- 함수의 프로포타입 객체는 `Function.prototype` 이며 이것도 함수

```javascript
function phone(number) {
  return number;
}

console.log(phone.__proto__ === Function.prototype);
console.log(Object.getPrototypeOf(phone) === Function.prototype);
```

### 6-6. prototype 속성

- 함수 객체만 가지고 있는 프로퍼티
- 함수 객체가 생성자로 사용될 때 생성된 객체의 부모 역할을 하는 객체를 가르킴
- 함수가 생성될 때 만들어지며 `constructor` 프로퍼티를 가지는 객체를 가지는 객체를 가리킴

> 함수는 생성자 함수로 사용될 가능성이 있기 때문에

```javascript
function phone(number) {
  return number;
}

console.log(phone.__proto__ === Function.prototype); // true ①
console.log(phone.__proto__ === phone.prototype);   // false
console.log(phone.prototype.constructor === phone); // true ②
console.log(phone.__proto__.constructor === phone.prototype.constructor); // false
```

## 7. 함수 호출 패턴에 따른 this의 참조값

### 7-1. 함수 호출 패턴

전역객체는 객체중에 가장 상위 객체인데 딱 유일한 하나이며 browser에서는 'window' node에서는 'global'을 포함

```javascript
// browser console
this === window // true

// in Terminal - Node
this === global // true
```

### 7-2. 메소드 호출 패턴

함수 자체가 객체의 Property면 메소드 호출 패턴으로 호출

> 메소드 내부에 this는 메소드를 호출한 객체에 바인딩됨

```javascript
function Person(name) {
  this.name = name;
}

Person.prototype.getName = function() {
  return this.name;
}

var me = new Person('Park');
console.log(me.getName());

Person.prototype.name = 'Woo';
console.log(Person.prototype.getName());
```

### 7-3. 생성자 호출 패턴

기존 함수에 new 연산자를 붙여서 호출하면 해당 함수는 생성자 함수로 동작

#### 동작 방식

1. 빈 객체 생성과 동시에 this 바인딩

   **순서**

   - 빈 객체를 만듬
   - this를 빈 객체를 가리킴
   - 마지막에 자신의 프로토타입 객체로 설정

2. this를 통한 property 생성

3. 생성된 객체를 반환함

   - 반환문이 없는 경우, this에 바인딩 되어있는 새로운 객체를 반환
   - 반환문이 this가 아닌 다른 객체를 반환하는 경우, this가 아닌 해당 객체가 반환

```javascript
var Person = function(name) {
  // 생성자 함수 코드 실행 전 -------- 1
  this.name = name;  // --------- 2
  // 생성된 함수 반환 -------------- 3
}

var me = new Person('Lee');
console.log(me.name);
```

