# JS 클래스(생성자함수, this, ES6 Classes, 상속/확장)


# 생성자 함수(prototype)

```javascript
const heropy = {
  firstName: 'Heropy',
  lastName: 'Park',
  getFullName: function(){
    return `${this.firstName} ${this.lastName}`
  }
}
console.log(heropy.getFullName())

const neo = {
  firstName: 'Neo',
  lastName: 'Smith',
  getFullName: function(){
    return `${this.firstName} ${this.lastName}`
  }
}
console.log(neo.getFullName())
```
```plaintext
위와 같은 방법으로는 비효율적(메모리 누수)
따라서 아래와 같이 작성한다.
```
---
```javascript
// 함수를 파스칼 표기법(PascalCase)으로 사용해서
// 해당 함수가 생성자 함수인 것을 알게 한다.
function User(first, last){
  this.firstName = first
  this.lastName = last
}

User.prototype.getFullName = function(){
  return `${this.firstName} ${this.lastName}`
}

const heropy = new User('Heropy','Park')
const amy = new User('Amy', 'Clarke')
const neo = new User ('Neo', 'Smith')

console.log(heropy.getFullName())
console.log(amy.getFullName())
console.log(neo.getFullName())


// "" {}  [] 
// 특정 기호로 데이터를 만들어 내는 것을
// 리터럴이라고 한다.



```

# this

## 일반(Normal) 함수는 호출 위치에서 따라 this 정의!
## 화살표(Arrow) 함수는 자신이 선언된 함수 범위에서 this 정의!

```javascript
const heropy = {
  name: 'Heropy',
  normal: function () {
//normal() {  <=이와 같이 축약해서 작성할 수 있다.
    console.log(this.name)
  },
  arrow:() => {
    console.log(this.name)
  }
}
heropy.normal() 
// this가 heropy
// Heropy를 출력  

heropy.arrow() 
// this가 안 정해져있음
// undefined를 출력
```
---
```javascript
const amy = {
  name: 'Amy',
  normal: heropy.normal,
  arrow: heropy.arrow
}
amy.normal()
// this가 heropy
// Heropy를 출력
amy.arrow()
// this가 안 정해져있음
// undefined를 출력
```
---
```javascript
  function User(name){
    this.name = name
  }
  User.prototype.arrow = () => {
    console.log(this.name)
  }

  const heropy = new User('Heropy')

  heropy.normal()
  heropy.arrow()

```
```javascript

const timer ={
  name:'Heropy!!',
  timeout: function () {
    setTimeout(function () { // 일반(Normal)의 경우 undefined
      console.log(this.name) // 화살표(Arrow)의 경우 Heropy!!
    }, 2000)
  }
}
timer.timeout()
```
# ES6 Classes

```javascript

// function User(first, last){
//   this.firstName = first
//   this.lastName = last
// }

// User.prototype.getFullName = function(){
  //   return `${this.firstName} ${this.lastName}`
// }

class User {
  constructor(first, last) {
    this.firstName = first
    this.lastName = last
  } 
  getFullName(){
    return `${this.firstName} ${this.lastName}`
  }
}

const heropy = new User('Heropy','Park')
const amy = new User('Amy', 'Clarke')
const neo = new User ('Neo', 'Smith')

console.log(heropy.getFullName())
console.log(amy.getFullName())
console.log(neo.getFullName())
```

# 상속(확장)

```javascript
class Vehicle {
  constructor(name, wheel){
    this.name = name
    this.wheel = wheel
  }
}
const myVehicle = new Vehicle('운송수단', 2)
console.log(myVehicle)

class Bicycle extends Vehicle {
  constructor(name, wheel){
    super(name, wheel)
  }
}
const myBicycle = new Bicycle('삼천리', 2)
const daughtersBicycle = new Bicycle('세발', 3)

console.log(myBicycle)
console.log(daughtersBicycle)

class Car extends Vehicle {
  constructor(name, wheel, license) {
    super(name wheel)
    this.license = license
  }
}
const myCar = new Car('벤츠', 4, true)
const daughtersCar = new Car('포르쉐', 4, flase)

console.log(myCar)
console.log(daughtersCar)

```