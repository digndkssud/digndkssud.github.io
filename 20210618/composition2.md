# App => App.Composition
## App에 있는 코드를 보다
## 간결하게 만들어준다.

# ref, computed, watch, onMounted
---
# App.vue
```vue
<template>
  <h1 @click="increase">
    {{ count }} / {{ doubleCount }}
  </h1>
  <h1 @click="changeMessage">
    {{ message }} / {{ reversedMessage }}
  </h1>
</template>

<script>
export default {
  data(){
    return {
      count: 0,
      message: 'Hello world!'
    }
  },
  computed: {
    doubleCount(){
      return this.count*2
    },
    reversedMessage(){
      return this.message.split('').reverse().join('')
    }
  },
  watch: {
    message(newValue){
      console.log(newValue)
    }
  },
  created() {
    console.log(this.message)
  },
  mounted() {
    console.log(this.count)
  },
  methods: {
    increase(){
      this.count += 1;
    },
    changeMessage(){
      this.message = 'Good?!'
    }
  }
}
</script>
```
# App.Composition.vue
```vue
<template>
  <h1 @click="increase">
    {{ count }}
  </h1>
  <h1 @click="changeMessage">
    {{ message }}
  </h1>
</template>

<script>
import { ref, computed, watch, onMounted } from 'vue'

export default {
  // setup은 컴포넌트가 생성된 직후에 동작함. 
  setup() {
    const count = ref(0)
    const doubleCount =computed(() => count.value*2)
    function increase(){
      count.value += 1
    }
    
    const message = ref('Hello world!')
    const reversedMessage = computed(() => {
      return message.value.split('').reverse().join('')
    })
    watch(message, newValue => {
      console.log(newValue)
    })
    function changeMessage(){
      message.value = "Good?!"
    }
    //created() = setup()
    console.log(message.value)

    onMounted(() => {
      console.log(count.value)
    })

    return {
      count,
      doubleCount,
      increase,
      message,
      reversedMessage,
      changeMessage
    }

  }
}
</script>
```