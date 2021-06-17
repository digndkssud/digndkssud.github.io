# component - Emit
## App.vue에서 사용할 이벤트를
## MyBtn.vue의 emits에서 설정해준다.
---
## v-model을 통해 쌍방향 
## msg에 변화가 일어나면
## chageMsg 메소드를 실행 시킨다

# MyBtn.vue
```vue
<template>
  <div class="btn">
    <slot></slot>
  </div>
  <h1 @dblclick="$emit('click', $event)">
    ABC
  </h1>
  <input
    type="text"
    v-model="msg" />
</template>

<script>
export default {
  emits: [
    'click',
    'changeMsg'
  ],
  data(){
    return {
      msg: ''
    }
  },
  watch: {
    msg(){
      this.$emit('changeMsg', this.msg)
    }
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
    @heropy="log"
    @change-msg="logMsg">
    Banana
  </MyBtn>
</template>

<script>
import MyBtn from '~/components/MyBtn'

export default {
  components:{
    MyBtn
  },
  methods: {
    log(event) {
      console.log('Click!!')
      console.log(event)
    },
    logMsg(msg){
      console.log(msg)
    }
  }
}
</script>
```