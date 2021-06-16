# chage & v-model.lazy 
## 값을 입력 후 enter, tap, 바깥 쪽 클릭해야 값이 갱신

```vue
<template>
  <h1>{{ msg1 }}</h1>
  <!-- enter, tap, 바깥 쪽 클릭 -->
  <input
    type="text"
    :value="msg1"
    @change="msg1 = $event.target.value" />
  <h1>{{ msg2 }}</h1>
  <input
    type="text"
    v-model.lazy="msg2" />
</template>

<script>
export default {
  data(){
    return {
      msg1: '단방향은 change',
      msg2: '양방향은 v-model.lazy'
    }
  },
  watch: {
    msg(){
      console.log(typeof this.msg)
    }
  }
}
</script>
```

---

# trim
## 앞뒤 공백 제거
```vue
<template>
  <h1>{{ msg }}</h1>
  <input
    type="text"
    v-model.trim="msg" />
</template>

<script>
export default {
  data(){
    return {
      msg : 'Hello world'
    }
  },
  watch: {
    msg(){
      console.log(this.msg)
    }
  }
}
</script>
```