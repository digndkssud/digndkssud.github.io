# 개발 서버 실행과 빌드  


```bash
$ parcel index.html
```

```json
package.json에 있는

"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },

  =>

  "scripts": {
    "dev": "parcel index.html",
    //개발용
    "build": "parcel build index.html"
    //유저용
  },
```

```bash

$ npm run dev
// index.html의 문서를
//http://localhost:1234의 주소로 열어준다.

```

---

```javascript

import _ from 'lodash'
//import를 통해 lodash를 `_`라는 이름으로 사용한다.

```
