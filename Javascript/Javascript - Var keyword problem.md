# Javascript var 키워드의 문제점

## 1. 중복 선언

변수에서 기본자료형은 중복 선언이 가능

```javascript
var score = 1;

console.log(score); // 1

var score = 100;

console.log(score); // 100
```

## 2. var 키워드 생략

변수 선언시 var 키워드를 생략이 가능하며 var 키워드 생략시 변수는 전역 변수가 됨

```javascript
score = 1;

console.log(score); // 1
```

## 3. 동적 타이핑

하나의 변수에 여러 `Data type`을 대입할 수 있음

```javascript
var score = 1; 
console.log(typeof(score)); // type: number

score = '1';   
console.log(typeof(score)); // type: string

score = [];
console.log(typeof(score)); // type; object
```

## 4. 변수 호이스팅 (Variable Hoisting)

모든 선언문은 호이스팅으로 인해 변수를 선언 이전에도 참조 가능하며 값은 `undefined`로 출력

```javascript
console.log(score); // undefined

var score = 1;

console.log(score); // 1
```

>  자세한 내용은 <a href="http://jinwoopark94.github.io/2018/02/14/javascript-hoisting/" >호이스팅</a>을 참고

## 5. Function-level scope

Javascript는 다른 언어들과 같이 block-level-scope를 가지지 않고, function-level scope를 가지고 있으므로 전역변수의 남발 현상이 일어남

- Function-level scope : 함수내의 변수는 함수 내부에서만 유효하며 지역변수라고 부르며 함수 외부에서는 해당 변수를 참조할 수 없음
- Block-level scope : 코드 블럭(`{ }`) 내부에 선언된 변수는 코드 블록 내에서만 유효하며 코드 블럭(`{ }`) 외부에서는 참조할 수 없음

```javascript
{
	var score = 1;
}

console.log(score);  // 1

function checkVal(){
  var chkval = 3;
}

console.log(chkval); // Error : chkval is not defined 
```