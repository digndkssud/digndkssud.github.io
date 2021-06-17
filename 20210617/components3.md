# components - Slot

## App.vue의 컨텐츠가 없을 때
## MyBtn에 있는 컨텐츠를 노출 시킴
---
# Named slot 
## slot에 name을 부여하여
## 관리를 용이하게 함
---
# MyBtn.vue
```vue
<template>
  <div class="btn">
    <slot name="icon"></slot>
    <slot name="text"></slot>
  </div>
</template>

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
  <MyBtn>
    <template #text>
      <span>Banana</span>
    </template>
    <template #icon>
      <span>(B)</span>
    </template> 
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