# 구조 분해 할당 (Destructuring assignment)
## 비구조화 할당

```javascript
const user = {
  name: 'Heropy',
  age: 85,
  email: 'thesecon@gmail.com'
}

const { name: heropy, age, email, address } = user
// 만약 name이라는 마음이 안 들경우에 
// 위와 같이 설정을 하면
// ${heropy}로 사용가능하다.
// E.g, user.address

console.log(`사용자의 이름은 ${heropy}입니다.`)
console.log(`${heropy}의 나이는 ${age}세입니다.`)
console.log(`${heropy}의 이메일 주소는 ${email}입니다.`)
console.log(address)

const fruits = ['Apple', 'Banana', 'Cherry']
const [a, b, c, d] =fruits
console.log(a, b, c, d)

const [, b] = fruits
console.log(b)
// Banana만 출력하고 싶을 때
```