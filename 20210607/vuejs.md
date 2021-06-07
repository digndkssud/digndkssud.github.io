# vuejs

```js
$ npm install -g @vue/cli

$ vue create vue3-test
// vue3-test라는 폴더를 생성 

```

# vue cil

```js
// vue cli 터미널에서 vue를 사용할 수 있게한다.
//확장 프로그램에서 
Vetur=> 코드 하이라이트 처리를 해준다.
```
---
# 작성 방법

# App.vue
```js
<template>
  <h1>{{ message }}</h1>
</template>

<script>
export default {
  data(){
    return{
      message: 'Hello Vue!!!'
    }
  }
}
</script>
```
---
# main.js

```js
import { createApp } from 'vue'
import App from './App.vue'

createApp(App).mount('#app')
```
---
# index.html
```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <meta charset="UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Webpack project!</title>
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css">
</head>
<body>
  <div id="app"></div>
</body>
</html>
```


# 확장자명

## webpack.config.js 
```js
// 파일 확장자명을 안 적어도 되도록 미리 설정.
module.exports = {
  resolve:{
    extensions:['.js', '.vue']
  }

// 이미지 부분.
$ npm i -D file-loader


 module: {
    rules: [
      {
        test: /\.(png|jpe?g|gif|webp)$/,
        use:'file-loader'
      }
    ]
  }

```

