# 속성 상속(Atrribute Inheritance)
## inheritAttrs => 연결되는 최상위 루트의 연결 여부를 결정해서 사용한다.
##
---
# MyBtn.vue

```vue
<template>
  <div class="btn">
    <slot></slot>
  </div>
  <h1
    :class="$attrs.class"
    :style="$attrs.style"
    :title="$attrs.title"></h1>
  <h1 v-bind="$attrs"></h1>
</template>

<script>
export default {
  inheritAttrs: false,
  created(){
    console.log(this.$attrs)
  }
}
</script>

<style scoped>
  .btn{
    display: inline-block;
    margin: 4px;
    padding: 6px 12px;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;
  } 
</style> 
```
---
# App.vue

```vue
<template>
  <MyBtn
    class="heropy"
    style="color:red;"
    title="Hello world!">
    Banana
  </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'
export default {
  components:{
    MyBtn
  }
}
</script>
```