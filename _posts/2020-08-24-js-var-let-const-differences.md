---
title: "var vs let vs const 과 호이스팅(Hoisting)"
date: 2020-08-24 
categories: reactjs javascript 
---

# var vs let vs const
1. var 
- function-scoped 
- 변수 재선언이 가능

```
var tmp = 'hello world'
console.log(tmp) //hello world

var tmp = 'hw'
console.log(tmp) // hw
```

-> 이 문제로 인해 ES6 이후에 `let`과 `const`가 추가 됨

2. let, const 
- block-scoped
- let은 변수에 재할당 가능, const는 변수 재할당 불가능

```
let tmp = 'test'
let tmp = 'test2' // Uncaught SyntaxError: Identifier 'tmp' has already been declared
tmp = 'test2' // 가능 


const tmp2 = 'test'
const tmp2 = 'test2' // Uncaught SyntaxError: Identifier 'tmp2' has already been declared
tmp2 = 'test2' // Uncaught TypeError:Assignment to constant variable.

```

- const는 선언과 동시에 할당되어야 한다. (재선언과 재할당이 모두 불가하다.) 



#호이스팅(Hoisting) 

<https://ojava.tistory.com/144>
<https://gist.github.com/LeoHeo/7c2a2a6dbcf80becaaa1e61e90091e5d>

`호이스팅(Hoisting)` 이란, 함수 안에 있는 `선언`들을 모두 끌어올려서 해당 함수 유효 범위의 최상단에 선언하는 것 

아래는 <https://velog.io/@bathingape/JavaScript-var-let-const-%EC%B0%A8%EC%9D%B4%EC%A0%90>의 호이스팅 내용을 요약정리 한 것이다. 


```
console.log(foo); // undefined
var foo;
console.log(bar); // Error: Uncaught ReferenceError: bar is not defined
let bar;
```

위에서 보는 바와 같이 var은 undefined이 출력되나 let은 ReferenceError에러가 발생한다. 

let으로 선언된 변수가 일시적 사각지대(Temporal Dead Zone; TDZ)에 빠지기 때문이다. 

변수는 `선언단계` > `초기화 단계` > `할당단계` 에 걸쳐 생성된다. 

var은 선언단계와 초기화 단계가 한번에 이루어지는 반면,

let은 선언단계와 초기화 단계가 분리되어 진행된다. 그래서 호이스팅으로 선언단계는 수행되었지만 초기화단계는 수행되지 않아서 에러가 발생한다. 

```
// 스코프의 선두에서 선언 단계가 실행된다.
// 아직 변수가 초기화(메모리 공간 확보와 undefined로 초기화)되지 않았다.
// 따라서 변수 선언문 이전에 변수를 참조할 수 없다.

console.log(foo); // ReferenceError: foo is not defined

let foo; // 변수 선언문에서 초기화 단계가 실행된다.
console.log(foo); // undefined

foo = 1; // 할당문에서 할당 단계가 실행된다.
console.log(foo); // 1
```




