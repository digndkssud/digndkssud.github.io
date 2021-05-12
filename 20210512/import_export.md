# 가져오기, 내보내기


```javascript

import _ from 'lodash' // From `node_modules`!
import getType from './getType' // getType.js
import { random, user as heropy } from './getRandom' // getRandom.js
// 이름을 정해서 나오는 export는 {}로 감싸주어야한다!!!!
// 또한, 한 개 이상의 것들을 export할 수 있다.
// as 키워드로 import하는 곳에서 이름 지정 가능

import * as R from './getRandom'
// 여러 내용을 한꺼번에 가져올 때 * <=를 사용해서 가져온다.

console.log(_.camelCase('the hello world'))
console.log(getType([1,2,3]))
console.log(random(),random())
console.log(R)

```