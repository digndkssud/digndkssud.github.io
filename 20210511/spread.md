# 전개 연산자(spread)

```javascript
const fruits = ['Apple', 'Banana', 'Cherry', 'Orange']
console.log(fruits)
console.log(...fruits)
/// console.log('Apple', 'Banana', 'Cherry')

function toObject(a, b, ...c){ // ...c는 rest parameter
// a에는 Apple, b에는 Banana, c에는 나머지!
  return {
    a: a,
    b: b,
    c: c
  }
}
const toObject = (a, b, ...c) => ({a, b, c})
// 축약형

console.log(toObject(...fruits))
// ...은 전개연산자
```