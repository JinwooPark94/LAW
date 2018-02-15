# 객체(Object)란?

나 자신(Subject)이 아닌 모든 인식가능한 것들을 객체라고 하며 기본자료형을 제외한 나머지 데이터와 그 데이터가 관련되는 `동작(절차, 방법, 기능)`을 모두 포함하는 것

> 이름과 값의 쌍인 속성(Property)들을 포함하는 컨테이너



## 속성(Property) 란?

객체안에서 이름과 값으로 구성됨

- 이름 : 빈 문자열을 포함하는 문자열과 숫자

  > 숫자를 쓰면 내부적으로 문자열로 바꿈 
  >
  > 예) 숫자 1을 썼다고 가정했을때 문자열 1로 바꿈

- 값 : `undefined`를 제외한 모든 값

```javascript
var container {
  name  : 'Jinwoo`s container';
  // 이름 : 값
}
```



## Method 란?

객체안에서 속성(Property)값에 `동작(절차, 방법 기능)`을 갖고 있는 것

> 결론 : 객체 안에 있는 함수

```javascript
var person = {
  name : 'Jin', // Property
  age : '100', // Property
  speak : function(){}// Method
  // 이름 : 값(함수: 동작-> 절차, 방법, 기능)
}
```



# 객체 생성 방법

## 1. 객체 리터럴

중괄호를 시작으로 생성하며 `{ }`안에 아무 것도 입력하지 않으면 빈 객체로 생성되고 입력시  `property name : property value`를 기술하여 생성가능

```javascript
var emptyObject = {}; // 빈 객체 생성

var person = { // 객체 생성
 name : 'Jin', 
 // property name : name, property value : 'Jin'
 age : '100', 
 // property name : age, property value : '100'
 speak : function(){} // Method
 // property name : speak, property value : function(){}
};
```



## 2. Object() 생성자 함수

New 연산자와 Object() 생성자 함수를 이용하여 빈 객체를 생성 가능하고 이후 객체 안에 Property를 추가를 하는 방식

```javascript
var person = new Object(); // 빈 객체 생성

person.name = 'Jin', 
// person의 객체에 name이 Jin인 Property를 추가
person.age = '100',
person.speak = functioon(){
	console.log("안녕 난 " + person.name + "이야");
}
```

> 브라우저안에 있는 자바스크립트 엔진은 우리(개발자?)를 위해서 내장 함수인 Object() 생성자 함수를 통해 단순화 시킨 위에 1번 객체 리터널 방식의 축약법임



## 3. 생성자 함수

우리가 원하는 객체를 만들기 위해서 함수를 정의 할 수 있는 방식

> Java에서의 Class 방식이며 중복을 제거하기 위해 만들어진 함수 

- 일반적으로 대문자로 시작 (함수 구별하여 기술 혼란을 방지하기 위해서)
- 속성(Property)값만 다른 여러개의 객체를 생성할때 사용

```javascript
function Person(name, gender) {
  this.name = name;
  this.gender = gender;
  this.speak = functioon(){
	console.log("안녕 난 " + this.name + "이야");
  };
}

// 인스턴스의 생성
var person1 = new Person('Park', 'male');
var person2 = new Person('Woo', 'female');

// 여기서 person1이 실행되면 Person이라는 함수에 'Park', 'male'이라는 매개 변수를 가지고 실행하여 함수안에 this.name 값에 'Park'이 들어가고 this.gender에 'male' 이라는 값이 들어가며 결국 person1의 객체의 name 값은 'Park', gender 값은 'male'이 들어감
```



## 여기서 잠깐 !! 

### 어떤 상황때 리터널 방식과 생성자 방식을 사용할까?

|     리터널 방식     |     생성자 방식     |
| :------------: | :------------: |
| 객체를 하나만 만들때 유리 | 객체를 여러개 만들때 유리 |

> 강사님 曰 : 둘중에 아무거나 하나 만들어보고 삽질을 통해 얻자. 사용방법을 터득하면 자신의 Javascript 레벨이 한 단계 올라감

------



## 객체 프로프티 접근

### 프로퍼티 이름

기본적으로 `문자열`을 포함하지만 문자열 이외에도 `숫자`를 포함하는데 숫자는 암묵적 형변환으로 인해 문자열로 바뀜

- Property 이름의 문자열이므로 따음표('', "")를 사용

  - 사용 가능한 유효한 이름일 경우 따음표 생략 가능

    > 유효한 이름이 아닌 경우 : 'first-name' (캐밥표기법)

- 예약어는 사용하면 안됨



### 프로퍼티 값 읽기

- 마침표(.) 표기법

- 대괄호([ ]) 표기법

  - 프로퍼티 이름과 마찬가지로 유효한 이름이 아닌 캐밥 표기법으로 될때 사용 

    > 예) person['first-name']

```javascript
var person = {
  'first-name': 'jinwoo',
  'last-name': 'Park',
  1: 10
};

console.log(person);

console.log(person.first-name);    // NaN: undefined-undefined
console.log(person[first-name]);   // ReferenceError: first is not defined
console.log(person['first-name']); // 'jinwoo'

console.log(person['1']); // 10
console.log(person[1]);   // 10 정수형인 1을 내부적으로 문자열 1로 바꾸므로
console.log(person.1);    // SyntaxError
```

> 객체에 존재하지 않는 속성(Property)를 참조하면 `undefined`를 반환

### 프로퍼티 값 변경

객체로 접근하여 프로퍼티 값을 새롭게 변경

```javascript
var person = {
  firstName: 'jinwoo',
  lastName: 'Park'
};

person.firstName = 'haha';
console.log(person.firstName); // 'haha'
```

### 프로퍼티 동적 생성

빈 객체를 만든 상태에서 프로퍼티를 추가할 경우 사용

```javascript
var person = {
  firstName: 'jinwoo',
  lastName: 'Park'
};

person.age = '20';
console.log(person.age); // '20'
```

> 위와 같은 방법으로 생성이 가능하지만 코드에 사용하지 않는 것이 좋음

### 프로퍼티 삭제

`delete`라는 명령어를 사용하여 삭제

```javascript
var person = {
  firstName: 'jinwoo',
  lastName: 'Park',
  age : 20
};

delete person.age;
console.log(person.age); // undefined
```

> 위와 같은 방법으로 삭제가 가능하지만 코드에 사용하지 않는 것이 좋음

## 여기서 잠깐 !! 

### 인스턴스(instance)란 무엇일까?

객체를 생성하기 위해 만들어진 또 다른 객체를 `인스턴스`라고 함

#### 특징

- 객체가 가지고 있는 `Property`와 `Method`를 상속 받음

#### 결론

**Javascript에서 인스턴스(instance)란 new 연산자와 생성자 함수를 통해 만든 객체**