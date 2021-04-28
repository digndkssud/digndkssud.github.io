# JAVASCRIPT-typeOf

JAVASCRIPT 특수한 상황 아니면 세미콜론 사용 X  
틀렸다고 하면 빨간 밑줄 나오니 괜찮

```javascript

파일 타입 확인


console.log(typeof "hello world")
// string
console.log(typeof 123)
// number
console.log(typeof true)
// boolean
console.log(typeof undefined)
// undefined
console.log(typeof null)
console.log(typeof {})
console.log(typeof [])
// object


function getType(data){
  return Object.prototype.toString.call(data).slice(8,-1)
}
console.log(getType(123))
// Number
console.log(getType(false))
// Boolean
console.log(getType(null))
// null
console.log(getType({}))
// Object
console.log(getType(Array))
// Array
```

getType을 어디서든 사용할 수 있게 지정해준다.

getType.js 파일 생성

```javascript

export default function getType(data){
  return Object.prototype.toString.call(data).slice(8,-1)
}

다른 곳에서 메소드를 사용하기 위해서는
해당 메소드를 사용하고자 하는 js파일에서

import getType from './getType'를 입력한다.


```