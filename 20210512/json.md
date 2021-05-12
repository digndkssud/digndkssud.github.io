# JSON


### json 파일을 생성
```json
{
  "string": "HEROPY",
  "number": 123,
  "boolean": true,
  "null": null,
  "object": {},
  "array": []
}
```
---
### js파일에서 json파일을 사용

```javascript
import myData from './myData.json'

console.log(myData)

const user = {
  name: 'HEROPY',
  age: 85,
  emails: [
    'thsecon@gmail.com',
    'neo@zillinks.com'
  ]
}
console.log('user',user)

const str = JSON.stringify(user)
// 문자 데이터화
// 자바스크립트의 JSON화
console.log('str',str)
console.log(typeof str)

const obj = JSON.parse(str)
// 분석해서 자바스크립트의 실제 데이터로 변환
// JSON의 자바스크립트화
console.log('obj',obj)

```