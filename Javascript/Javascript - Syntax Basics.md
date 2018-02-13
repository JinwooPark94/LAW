# Javascript 기본 문법 및 기초

## 문법

### 1. 대소문자 구분

Script내에 변수, 함수 이름, 연산자 모두 대소문자 구분함

```javascript
// test와 Test는 서로 다른 변수임
var test;
var Test;
```

### 2. 식별자 (identifier)

식별자는 변수나 함수, 프로퍼티, 함수 매개변수의 이름을 가르키며 Javascript에서는 주로 카멜 케이스로 사용함

> ECMAScript의 내장 함수가 모두 카멜 케이스로 표기되어 있음

```javascript
// 카멜 케이스 : 첫 번째 문자는 소문자며 단어가 바뀔 때 대문자로 표기
var fastCar;
var myHouse;
var likeHARIBO;
```

### 3. 값 (literal)

여기서의 값을 보통 리터널이라 부름

> 리터널이란 : 변수 또는 상수에 저장되는 값 자체를 의미

```
2000 // literal : Number
'Hi Hello' // literal : String
{ name: 'Park', age: '25' } // literal : Object
['Spring','Summer']; // literal : Array
```

### 4. 표현식 (Expression)

하나의 값으로 평가될 수 있는 구문

> 구문은 표현식이 될 수 없음

```
10 * 6             // 60
'Hi' + ' ' + 'bro' // 'Hi bro'
```

### 5. 구문 (Statement)

Script가 컴퓨터에 의해 단계별로 수행될 명령들

```
var x = 5;
```

예 ) 키워드 x라는 이름으로 변수를 생성하고 그 x라는 이름에 5라는 값을 넣어라

```
var z = x + y;
```

예 ) 키워드 z라는 이름으로 변수를 생성하고 x,y라는 값을 가져와서 더한 다음 z에 넣어라

### 6. 변수 (Variable)

변수는 위치를 기억하는 저장소이며 값을 저장, 참조하기 위해 사용

```
var number;  // 변수의 선언과 초기화
number = 6;
```

예) number로 변수를 선언하고 변수 number에 6을 할당해라

### 7. 주석

Javascript에서는 주석을 C언어와 같은 스타일로 표기

- 한 줄 주석은 아래와 같이 슬래시(`/`)문자 두 개로 나타냄

```javascript
// 한 줄 주석
```

- 여러 줄 주석은 시작 형태는 (`/*`) 마지막 형태는  (`*/`)로 끝냄

```javascript
/*
   여러 줄 주석
*/
```

> 최대한 주석은 사용 안 하는 것이 좋은 코드

### 8. 문장

8-1. Javascript에서는 각 문장을 세미콜론으로 종료함

> Javascript에서 암묵적으로 세미콜론이 있었으리라고 생각되는 부분에 세미콜론을 추가해서 문법 에러는 나지않음

```javascript
var snack = 'HARIBO'     // 세미콜론은 안붙여도 에러 X
var stomachFull = false; // 문장의 마지막에는 세미콜론을 븥이는 것을 권장 
```

8-2. 여러 문장을 코드 블록인 중괄호 `{ }`을 사용하여 합칠 수 있음

> 코드 블록을 사용하면 의도를 더 명확하게 표현 가능하고 수정할 때 에러가 생길 가능성이 적어짐

```javascript
var foo = 1;
var boo = 2;
var sum = 0;

function sum(foo, boo){
  sum = this.foo + this.boo;
  alert(sum);
}
```



## 키워드와 예약어

#### 1. 키워드

Javascript에서 키워드는 식별자나 프로퍼티 이름에 사용이 불가능함

| break        | default     | function       | return     | var        |
| ------------ | ----------- | -------------- | ---------- | ---------- |
| **case**     | **delete**  | **if**         | **switch** | **void**   |
| **catch**    | **do**      | **in**         | **this**   | **while**  |
| **const**    | **else**    | **instanceof** | **throw**  | **with**   |
| **continue** | **finally** | **let**        | **try**    | **typeof** |
| **debugger** | **for**     | **new**        |            |            |

ECMAScript 5에서는 예약어 규칙이 달라져서 아래 목록은 일반 모드에서 예약어로 사용하는 키워드

| class     | enum       | extends    | super |
| --------- | ---------- | ---------- | ----- |
| **const** | **export** | **import** |       |

#### 2. 예약어

Javascript에서 예약어는 이미 쓰임이 정해져 있는 키워드를 의미

| abstract         | enum          | int          | short         | boolean     |
| ---------------- | ------------- | ------------ | ------------- | ----------- |
| **export**       | **interface** | **static**   | **byte**      | **extends** |
| **long**         | **super**     | **char**     | **final**     | **native**  |
| **synchronized** | **class**     | **float**    | **package**   |             |
| **const**        | **goto**      | **private**  | **transient** |             |
| **implements**   | **protected** | **volatile** | **double**    |             |
| **public**       | **debugger**  | **import**   | **throws**    |             |

## 참고 사이트

 Javascript MDN

http://poiemaweb.com 