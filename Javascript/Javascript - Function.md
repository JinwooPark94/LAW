# 함수(Function)

어떤 작업을 수행할때 필요한 일련의 구문들을 그룹화하기 위한 개념으로 사용

## 1. 함수를 생성하는 방식

### 1-1. 함수 선언식

```javascript
function testFunction(number) {
  return number * number;
}
```

- 함수명 :  함수를 구별할 수 있는 식별자 역할 예) square
- 매개변수 목록 : 함수명 옆에 괄호로 구별하며 안에 콤마(,)로 분리함 예) number
- 함수 몸체 : 중괄호({})로 감싸며 `return` 문으로 결과를 반환

> 만약 return을 생략하면 return 값을 'undefined'를 결과값으로 반환

### 1-2. 함수 표현식

함수 선언식과 마찬가지로 동일하게 함수 리터널 방식으로 정의

```javascript
var test = function(number) {
  return number * number;
};
```

### 여기서 잠깐 !!

### 함수 선언식과 함수 표현식의 차이점은 무엇일까?

Javascript 엔진이 실행 컨텍스트에 데이터를 불러올 때 서로의 차이점이 있음

#### 함수 선언식

어떤 코드도 실행하기 전에 이미 모든 것들이 실행 컨텍스트에서 접근하여 실행 가능

```javascript
alert(sum(10, 20));
function sum(num1, num2){
  return num1 + num2;
}

// 결과는 결과값 30이 alert창으로 보여짐 
```

#### 함수 표현식

코드 실행이  해당 줄까지 진행하기 전에는 사용 할 수가 없음

```javascript
alert(sum(10, 20));
var sum = function(num1, num2){
  return num1 + num2;
};

// 결과는 예기치 못한 식별자 에러 발생!!
```

### 1-3. Function() 생성자 함수

함수 표현식과 함수 선언식이 결국 리터널 방식으로 정의되는데 결국 Function() 생성자 함수로 함수를 생성하는 것을 단순화 시킨 것

```javascript
var test = new Function('number', 'return number * number');
console.log(square(10)); // 100
```



## 2. 매개변수(parameter, 인수)

함수의 작업을 위해 추가적인 정보가 필요한 경우 매개변수를 지정하여 사용

### 매개 변수(인수) vs 인자

```javascript
// 매개 변수 - 인수
var foo = function (p1, p2) {
  console.log(p1, p2);
};

// 인자
foo(1); // 1 undefined
```



## 3. Call-by-value , Call-by-reference

### 3-1. Call-by-value (값에 의한 호출)

기본자료형은 값에 의한 호출로 동작하며 함수를 호출하여 매개변수를 변경해도 값은 변경되지 않음

```javascript
function foo(primitive) {
  primitive += 1;
  return primitive;
}

var x = 0;

console.log(foo(x)); // 1
console.log(x);      // 0
```

### 3-2. Call-by-reference (값에 의한 참조)

객체형(참조형)은 참조에 의한 호출로 동작하며 함수를 호출하여 매개변수를 변경하면 값이 변경됨

```javascript
function changeVal(primitive, obj) {
  primitive += 100;
  obj.name = 'Kim';
  obj.gender = 'female';
}

var num = 100;
var obj = {
  name: 'Lee',
  gender: 'male'
};

console.log(num); // 100
console.log(obj); // Object {name: 'Lee', gender: 'male'}

changeVal(num, obj);

console.log(num); // 100
console.log(obj); // Object {name: 'Kim', gender: 'female'}
```



## 4. 일급 객체(First class object)란?

함수도 객체이며 아래의 특징 5가지로 일급 객체라고 부름 

### 4-1. 무명 리터럴(무명 함수)로 표현 가능

```javascript
// 함수 표현식 방법
var sum = function(num1, num2){
  return num1 + num2;
};

// 함수 선언문 방법
function sum(num1, num2){
  return num1 + num2;
}
```

### 4-2. 변수나 배열, 객체에 할당 가능

```javascript
// 변수에 함수 할당
var foo = function(){ 
  return 'HARIBO'; 
};
console.log(foo()); // HARIBO

// 객체에 함수 할당
var boo = {};
boo.eat = function() {
  return 'HARIBO'; 
};
console.log(boo.eat()); // HARIBO
```

###4-3. 함수 파라미터(인자)로 전달 가능

```javascript
// 함수 리터널 방식으로 익명함수 func를 전달
var foo = function(func) {
    func();
}
```

### 4-4. 함수의 반환값(리턴값)으로 사용 가능

```javascript
// 함수 리터널 방식으로 return값을 함수로 반환
var foo = function() {
    // 함수를 리턴
    return function() {
        console.log('HARIBO');
    }
};

var boo = foo();
boo(); // HARIBO
```

### 4-5. 프로퍼티 생성 및 할당 가능

```javascript
// 함수 선언문 방식으로 add() 함수 정의
function sumNum(num1, num2){
  return num1 + num2;
};

sumNum.sum = add(1,2);
sumNum.whatFood = 'HARIBO';

console.log(sumNum.sum); // 3
console.log(sumNum.whatFood); // 'HARIBO'
```

## 5. 재귀함수란 ?

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

