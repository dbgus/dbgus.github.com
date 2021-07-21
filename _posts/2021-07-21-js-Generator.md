---
layout: post
title: 2021-07-21 TIL
subtitle: 
categories: TIL
tags: [TIL, javascript]
---
## javascript Generator 
### Generators란?
ES6에 추가된 문법으로 가장 큰 특징으로는 동작중 중간에 멈춘다면 다음 실행 때는 그 멈춘 지점에서 시작하는 특징을 가지고있습니다.



### Generators 문법
```javascript
// example
function* test() {
    console.log('1');
    yield 1;
    console.log('2');
    yield 2;
    console.log('3');
    yield 3;
}
const func = test()
console.log(func.next()) // 1, {value:1, done:false}
console.log(func.next()) // 2, {value:2, done:false}
console.log(func.next()) // 3, {value:3, done:false}
console.log(func.next()) // , {value:undefined, done:true}
```
Generators는 위와 같은 방식으로 동작합니다.

좀 더 자세한 설명을 하자면 일반 `function`에 `function*`으로 변경하면서 `Generators`로 변환된다.
(`*`는 어느 함수에서도 사용이 가능합니다)

Generators는 위 코드에서는 Generators function에서는 다른 함수와는 다르게 `return`이 없습니다. 대신에 `yield`라는 키워드가 존재하며 `yield`는 generators가 스스로 멈출 수 있도록 하는 연산자입니다. 
`generators`가 `yield`를 맞닥드릴 떄 마다 `generators`는 `yield`로 지정한 값을 반환합니다.

또한 `generators`가 `yield`를 만나 지정된 값을 반환 할 때 `return`된 값이 아닌 `yield`된 값이라고 하는 것이 더 정확할 것입니다.

```javascript
function* test() {
    console.log('1');
    yield 1;
    return 'returned'
    console.log('2');
    yield 2;
    console.log('3');
    yield 3;
}
```
기존에 만들었던 예제 코드에서 다음과 같이 `yield`와 더불어 `return`을 적게 된다면 `console.log('2')`부터는 실행이 되지 않고 끝나게 됩니다. (다만 `func.next()`을 줄이지 않았기 때문에 console에 로그에서는 return 이후는 `undefined`로 나올 것입니다.)
추가적으로 generators의 'yield' 값은 언제나 `generators object`로 반환이 됩니다. 즉, `return`으로 `generators`을 종료시켰다 해도 `generators object`로 반환이 될 것입니다.


---
### 참고
```출처
https://kamang-it.tistory.com/entry/JavaScript-16Generator%EC%99%80-Yield
https://codeburst.io/understanding-generators-in-es6-javascript-with-examples-6728834016d5
```