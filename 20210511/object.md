# Object.assign()

```javascript

const userAge = {
  // key: value
  name: 'Heropy',
  age: 85
}
const userEmail= {
  name: 'Heropy',
  email: 'thesecon@gmail.com'
}

const target = Object.assign({}, userAge, userEmail)
//첫번째 요소에 두번째 요소, 세번째 요소의 같은 복사한다.
console.log(target)
console.log(userAge)
console.log(target === userAge)

const a = { k: 123 }
const b = { k: 123 }
console.log(a === b)
```

# Object.keys()
```javascript

const user = {
  name: 'Heropy',
  age: 85,
  email: 'thesecon@gmail.com'
}

const keys = Object.keys(user)
console.log(keys)
// ['name', 'age', 'email']

console.log(user['email'])
// indexing 
// 결과값 :  thesecon@gmail.com

const values = keys.map(key => user[key])
// user[name], user[age] , user[email]
// => [Hropy, 85, thesecon@gmail.com]라는 배열이 values에 생성
console.log(values)
// 따라서 [Hropy, 85, thesecon@gmail.com]를 출력한다.
```