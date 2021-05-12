# Lodash 사용법!
## uniqBy, unionBy, find, findIndex, remove

# lodash.uniqBy(), lodash.unionBy()
## 중복되는 값 삭제.
```javascript
import _ from 'lodash'

const usersA = [
  { userId: '1', name: 'HEROPY'},
  { userId: '2', name: 'Neo'}
]
const usersB = [
  { userId: '1', name: 'HEROPY'},
  { userId: '3', name: 'Amy'}
]

const usersC = usersA.concat(usersB)
console.log('concat', usersC)
console.log('uniqBy', _.uniqBy(usersC,'userId'))
// lodash.uniqBy는 중복되는 값을 없애준다.
// 1개일 때 주로 사용
const usersD = _.unionBy(usersA, usersB, 'userId')
console.log('unionBy', usersD )
// lodash.unionBy는 중복되는 값을 없애준 후 병합을 도와준다.
// 2개 이상일 때 주로 사용
```

# lodash.find(), lodash.findIndex() , lodash.remove()

```javascript
const users = [
  { userId: '1', name: 'HEROPY' },
  { userId: '2', name: 'Neo' },
  { userId: '3', name: 'Amy' },
  { userId: '4', name: 'Evan' },
  { userId: '5', name: 'Lewis' }
]
const foundUser = _.find(users, { name: 'Amy'})
const foundUserIndex = _.findIndex(users, { name : 'Amy' })
console.log(foundUser)
console.log(foundUserIndex)

_.remove(users, { name: 'HEROPY' })
console.log(users)
  
```