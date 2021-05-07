# 함수(복습, 화살표 함수, 즉시 실행 함수, 호이스팅, 타이머함수, 콜백)

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

# 호이스팅(Hoisting)
## 함수 선언부가 유효범위 최상단으로 끌어올려지는 현상

```javascript

const a = 7

double()

const double = function(){
  console.log(a * 2)
}
// 위의 같은 상황에는 오류 발생
```

---

```javascript
const a = 7

double()

function double(){
  console.log(a * 2)
}
// 오류 발생 없음
```

# 타이머 함수
## setTimeout(함수, 시간) : 일정 시간 후 함수 실행
## setInterval(함수, 시간) : 시간 간격마다 함수 실행
## clearTimeout() : 설정된 Timeout 함수를 종료
## clearInterval() : 설정된 Interval 함수를 종료

```javascript

setTimeout(function () {
  console.log('Heropy!')
}, 3000) // 1000ms는 1초

setTimeout(() => {
  console.log('Heropy!')
}, 3000)
//화살표 함수 

const timer = setTimeout(() => { //setInterval도 대체 가능
  console.log('Heropy!')
}, 3000)

const h1El = document.querySelector('h1')
h1El.addEventListener('click', () =>{
  clearTimeout(timer)           //clearInterval(timer)도 대체 가능
})

```

# 콜백(Callback)
## 함수의 인수로 사용되는 함수
## setTimeout(함수, 시간)

```javascript
function timeout(callback) {
  setTimeout(() => {
    console.log('Heropy!')
    cb()
  }, 3000)
}
timeout(() => {
  console.log('Done')
})


```
