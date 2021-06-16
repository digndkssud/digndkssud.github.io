# Component
## 부모- 자식간의 데이터 통신

# Props
## componenet 안에서 어떻게 처리할지 정의

---
# MyBtn - 자식

```vue
`<template>
  <div
    :class="{ large }"
    :style="{ backgroundColor: color }"
    class="btn">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: {
    color:{
      type: String,
      default: 'gray'
    },
    large:{
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped lang="scss">
  .btn{
    display: inline-block;
    margin: 4px;
    padding: 6px 12px;
    border-radius: 4px;
    background-color: gray;
    color: white;
    cursor: pointer;
    &.large{
      font-size:20px;
      padding: 10px 20px;
    }
  } 
</style> 
```
---
# App.vue - 부모 

```vue
<template>
  <MyBtn>Banana</MyBtn>
  <MyBtn
    :color="color">
    <span style="color: red;">Apple</span>
  </MyBtn>
  <MyBtn
    large
    color="royalblue">
    Cherry
  </MyBtn> 
  <MyBtn>Cherry</MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
  components: {
    MyBtn
  },
  data(){
    return {
      color: '#000'
    }
  }
}
</script>
```