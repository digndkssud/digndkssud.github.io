# 이벤트 핸들링
## v-on:click = ""
## @click = ""

```vue
<template>
  <!-- 따로 인수를 넣어주지 않으면 event 객체를 인수로 받아들인다. -->

  <button @click="handler('hi',$event)">
    Click 1
  </button>
  <button @click="handler('what')">
    Click 2
  </button>
  <button @click="handler">
    Click 3
  </button>
</template>

<script>
export default {
  methods:{
    handler(msg, event) {
      console.log(msg)
      console.log(event)
    }
  }
}
</script>
```
---

```vue
<template>
  <button @click="handlerA(), handlerB()">
    Click me!
  </button>
</template>

<script>
export default {
  methods: {
    handlerA() {
      console.log('A')
    },
    handlerB() {
      console.log('B')
    }
  }
}
</script>
```