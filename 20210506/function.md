# 함수(복습, 화살표 함수, 즉시 실행 함수)

```javascript
function sum(x, y){
  return x + y  // 반환 및 종료
}

const a = sum(1, 3)
const b = sum(4, 12)

console.log(a)
console.log(b)
console.log(a + b)


function sum(){
  console.log(arguments)  
  // arguments에는 입력 받은 argument의 배열이 들어있다. 
  // ex) 7, 3
  return arguments[0] + arguments[1]
}

console.log(sum(7,3))

```

# 화살표 함수
## () => {} vs function () {}

```javascript
const dobule = function (x, y) {
  return x * 2
}

console.log('double: ', double(7))
```

---

```javascript
const doubleArrow = x => x * 2 // 축약형
const doubleArrow1 = (x, y) => x * y * 2 
const doubleArrow2 = ({name: 'Heropy'})
console.log('doubleArrow',doubleArrow(7))

```

# 즉시 실행 함수(IIFE, Immediately-Invoked Function Expression)

```javascript
const a = 7
function double(){
  console.log(a * 2)
}
double();

//권장!
  (function () {
    console.log(a * 2)
  }());

(function () {
  console.log(a * 2)
})();


```