# computed caching

```vue
<template>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
</template>

<script>
export default {
  data(){
    return{
      msg: 'Hello Computed!'
    }
  },
  computed:{
    // 캐싱 = > 미리 계산을 해두었고 그 이후의 값도 같으니 
    // 다시 계산할 필요없이 진행.
    // 읽기 전용
    // 최적화 가능!@!@!@!@

    reversedMessage(){
      return this.msg.split('').reverse().join('')
    }
  }
}
</script>
```

---

# Getter, Setter

```vue
<template>
  <button @click="add">
    ADD
  </button>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
  <h1>{{ reversedMessage }}</h1>
</template>

<script>
export default {
  data(){
    return{
      // Getter, Setter
      msg: 'Hello Computed!'
    }
  },
  computed:{
    // Getter
    // reversedMessage(){
    //   return this.msg.split('').reverse().join('')
    // }
    // Getter, Setter
    reversedMessage :{
      get(){
        return this.msg.split('').reverse().join('')
      },
      set(newValue){
        this.msg = newValue
      }
    }
  },
  methods:{
    // Setter
    add(){
      this.reversedMessage += '!?'
    }
  }
}
</script>
```
---
# watch 
## watch 부분에 기입한 메소드를 지켜보고 해당 메소드의 변화가 일어나면 동작한다.

```vue
<template>
  <h1 @click="changeMessage">
    {{ msg }}
  </h1>
  <h1 @click="changeMessage">
    {{ reversedMessage }}
  </h1>
</template>

<script>
export default {
  data(){
    return [
      msg: 'Hello?'
    ]
  },
  computed:{
    reversedMessage(){
      return this.msg.split('').reverse().join('')
    }
  },
  watch:{
    msg(newValue){
      console.log('msg',newValue)
    },
    reversedMessage(){
      console.log('reversedMessage', this.reversedMessage)
    }
  },
  methods:{
    changeMessage(){
      this.msg = 'Good!'
    }
  }
}
</script>
```
