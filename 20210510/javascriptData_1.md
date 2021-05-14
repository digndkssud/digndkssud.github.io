# JS 데이터(문자, Math, 배열)

```plaintext
string mdn
```
# 문자  

```javascript

const result = `Hello world`.indexOf('world')
consloe.log(result) 
// 검색하려는 단어가 처음 시작된 부분의 인덱스 값을 출력(6)
// 만약 일치하는 값이 없을 경우 -1을 반환


const str = 'Hello world'

console.log(str.indexOf('worl d') !== -1) 
//false

console.log(str.slice(0, 3))// 배열의 0부터 세번째 부분 짤라서 출력
console.log(str.replace('world','HEROPY'))// 첫번째 인수를 찾아서 두번째 인수의 값으로 교체

const str = 'thesecon@gmail.com'
console.log(str.match(/.+(?=@)/)[0])// thesecon 출력


const str = '     Hello world   '
console.log(str.trim())// 앞 뒤 공백 문자 제거 

```

# 숫자와 수학

```javascript
const pi = 3.14159265358979
console.log(pi)

const str = pi.toFixed(2)
// 숫자 데이터에만 사용가능
// 소수점 이하 N번째까지 표시

console.log(str)
console.log(typeof str)


const integer = parseInt(str)
const float = parseFloat(str)
// 숫자 데이터를 포함하고 있는 str을 정수나 소수점으로 변환한다.

console.log(integer) // 3
console.log(float) // 3.14
console.log(typeof integer, typeof float)
```

# Math 함수

```javascript
console.log('abs : ', Math.abs(-12))
//숫자의 절대값 (12)

console.log('min : ', Math.min(2, 8))
// 인수로 들어온 숫자 데이터 중에 작은 숫자를 확인

console.log('max : ', Math.max(2, 8))
// 인수로 들어온 숫자 데이터 중에 큰 숫자를 확인

console.log('ceil : ', Math.ceil(3.14))
// 숫자의 올림처리 (4)

console.log('floor : ', Math.floor(3.14))
// 숫자의 내림처리 (3)

console.log('round : ', Math.round(3.5))
// 숫자의 반올림 

console.log('random : ', Math.random())
```

# 배열

```javascript
// 공통 
const numbers = [1, 2, 3, 4]
const fruits = ['Apple', 'Banana', 'Cherry']

// .length

console.log(numbers.length) // 4
console.log(fruits.length)// 3
console.log([1,2].length)// 2
console.log([].length) // 0

// .concat()

console.log(numbers.concat(fruits))
// 두 개의 배열을 합하여 하나의 배열을 생성
// 원본 손상 x
console.log(numbers)
console.log(fruits)


// .forEach()
fruits.forEach(function(element, index, array){
  console.log(element, index, array) 
  // array는 사용 빈도가 떨어짐
})
 
fruits.forEach(function(fruit, i){
  console.log(fruit, i)
})


// .map()
const a = fruits.forEach(function(fruit, index){
  console.log(`${fruit}-${index}`)
}) 

const a = fruits.forEach((fruit, index) => {
  console.log(`${fruit}-${index}`)
})

console.log(a)

const b = fruits.map(function (fruit, index){
  return `${fruit}-${index}`
})

const b = fruits.map((fruit, index) => ({
  id: index,
  name: fruit
}))
console.log(b)

const c = fruits.map(function (fruit, index){
  return {
    id: index,
    name: fruit
  }
})
console.log(c)


// .filter()
const a = numbers.map(number => number < 3)
console.log(a)

const b = numbers.filter(number => number < 3 )
console.log(b)


// .find() .findIndex()
const a = fruits.find(fruit => {
  return /^C/.test(fruit)
  // ^은 시작의 의미 
}) 
console.log(a) // Cherry를 출력

const b = fruits.findIndex(fruit => {
  return /^C/.test(fruit)
})
console.log(b) // 2를 출력



// .includes()
const a = numbers.includes(3) // true
console.log(a)

const b = fruits.includes('HEROPY') // false
console.log(b)


// .push() .unshift()
// 원본 수정됨 주의!!!
numbers.push(5) // 배열 맨 뒤에 데이터 삽입
console.log(numbers)

numbers.unshift(0) // 배열 맨 처음에 데이터 삽입
console.log(numbers)


// .reverse()
// 원본 수정됨 주의!!
numbers.reverse()
fruits.reverse()

console.log(numbers)
console.log(fruits)


// .splice()
// 원본 수정됨 주의!!
numbers.splice(2, 2) 
// 인덱스 번호 2번에서 2개의 데이터를 지운다.
// 출력되는 값은 [1, 2]


numbers.splice(2, 0 , 999)
// 인덱스 번호 2번에서 0개의 데이터를 지운 후
// 999이라는 데이터를 끼워 넣는다


console.log(numbers)

```
