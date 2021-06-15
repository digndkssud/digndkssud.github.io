# 조건부 렌더링(v-if / v-show)
## v-show는 변환을 많이 해야할 때 사용하는 것이 좋음
## 또한 css의 display를 이용.

```vue
<template>
  <button @click="handler">
    Click me!  
  </button>
  <h1 v-if="isShow">
    Hello?!
  </h1>  
  <h1 v-show="isShow">
    Hello?!
  </h1> 
</template>

<script>
  export default {
  data(){
    return {
      isShow: false,
      count: 0
    }
  },
  methods: {
    handler(){
      this.isShow = !this.isShow
      this.count += 1
     }
    }
  }
</script>

```
