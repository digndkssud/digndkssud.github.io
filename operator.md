# 연산자


## 산술 연산자(arithmetic operator)  

```javascript
console.log(1 + 2)  // 3
console.log(5 - 7)  // -2
console.log(3 * 4)  // 12
console.log(10 / 2) // 5
console.log(10 % 3) // 1
```
## 할당 연산자(assignment operator)  

```javascript
let a = 2    // let 재할당 가능
// a = a + 1
a += 1 

console.log(a)

const a = 2 // const 재할당 불가

```

## 비교 연산자(comparison operator)

```javascript

const a = 1
const b = 1

console.log(a === b) // true


function isEqual(x,y){
  return x === y
}

console.log(isEqual(1, 1)) // true
console.log(isEqual(2, '2')) // flase
```
---

```javascript

const a = 1
const b = 3

console.log(a !== b) // true

console.log(a < b) // true

```

## 논리 연산자(logical operator) 

```javascript

const a = 1 === 1 
//1과 1을 비교한 결과를 a에 대입한다.
const b = 'AB' === 'AB'
const c = true

console.log(a) // true
console.log(b) // true
console.log(c) // true

console.log('&&: ', a && b && c)
// And 연산자 :  하나라도 false면 값은  false

console.log('||: ', a || c)
// Or 연산자 : 하나라도 true면 true

console.log('!: ', !a)
// Not 연산자 : 반대의 값을 반환

```

## 삼항 연산자(ternary operator)

```javascript
const a = 1 < 2 //true

if (a) {
  console.log('참')
} else {
  console.log('거짓')
}

=> console.log(a ? '참' : '거짓')
```