# localStorage

```javascript
const user = {
  name: 'HEROPY',
  age: 85,
  emails: [
    'thesecon@gmail.com',
    'neo@zillinks.com'
  ]
}

localStorage.setItem('user', JSON.stringify(user))
console.log(JSON.parse(localStorage.getItem('user')))
localStorage.removeItem('user')  

const str = localStorage.getItem('user')
// user라는 객체를 str에 저장
const obj = JSON.parse(str)
// str은 json이기 때문에 자바스크립트에서 활용할 수 있게
// JSON.parse()를 통해 변환
obj.age = 22
console.log(obj)
localStorage.setItem('user', JSON.stringify(obj))
// 추가 입력한 내용을 json으로 바꿔주기위해
// JSON.stringify()를 통해 변환 후 
// setItem으로 값을 입력한다.


```