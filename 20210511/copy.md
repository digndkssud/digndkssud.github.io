# 얕은 복사(Shallow copy)
### 객체만 복사하여 새 객체를 생성한다.
### 해당 메모리 주소의 값이 변경되면 원본 객체 및 복사 객체의 인스턴스 변수 값은 같이 변경된다.

```javascript
const user = {
  name: 'Heropy',
  age: 85,
  emails: ['thesecon@gmail.com']
}
const copyUser = user
console.log(copyUser === user)

user.age = 22
console.log('user', user)
console.log('copyUser', copyUser)

console.log('------')
console.log('------')
// 이 경우에는 user의 age 뿐만 아니라 copyUser 부분의 age도 바뀌어버린다.

const copyUser = Object.assign({},user)
// user가 가지고 있는 값을 새로운 메모리에 올린다.
console.log(copyUser === user)
user.age = 22
// Object.assign을 이용한 예

const copyUser = {...user}
// user가 가지고 있는 값들을 전개하여서 copyUser에 대입되고 새로운 메모리에 저장이 된다.
console.log(copyUser === user)
user.age = 22
// 전개 연산자를 이용한 예

user.emails.push('neo@zillinks.com')
console.log(user.emails === copyUser.emails)
console.log('user',user)
console.log('copyUser',copyUser)
```

#  깊은 복사(Deep copy)
### 새로운 메모리에 담고 인스턴스 변수까지 복사
### 전부를 복사하여 새 주소에 담기 때문에 참조를 공유하지 않는다.

```javascript
$ npm i lodash

//js 파일 부분에서
import _ from 'lodash'

const user = {
  name: 'Heropy',
  age: 85,
  emails: ['thesecon@gmail.com']
}
const copyUser = _.cloneDeep(user)
console.log(copyUser === user)

user.age = 22
console.log('user', user)
console.log('copyUser', copyUser)

console.log('------')
console.log('------')

user.emails.push('neo@zillinks.com')
console.log(user.emails === copyUser.emails)
console.log('user',user)
console.log('copyUser',copyUser)



```
