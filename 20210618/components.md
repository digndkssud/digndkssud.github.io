# Refs
## created()에서는 사용불가
## mounted()에서만 사용가능

# Hello.vue
```vue
<template>
  <h1 ref="hello">
    Hello world!
  </h1>
</template>

<script>
export default {
  // 생성된 직후
  created(){
    console.log(this.$refs.hello)
  },
  // 연결된 직후
  mounted() {
    // const h1El = document.querySelector('#hello')
    console.log(this.$refs.hello)
  }
}
</script>

```

# $el & $refs
--- 
# App.vue
```vue
<template>
  <Hello ref="hello" />
</template>

<script>
import Hello from '~/components/Hello'

export default {
  components: {
    Hello
  },
  mounted() {
    // 참조해서 쓰는 요소들을 불러 올 때는 $el
    console.log(this.$refs.hello.$el)
    // 요소가 두개 이상일 때는 자식 컴포넌트에서 refs해서 가져온다.
    console.log(this.$refs.hello.$refs.good)
  }
}
</script>
```
---
# Hello.vue
```vue
<template>
  <h1>
    Hello~
  </h1>
  <h1 ref="good">
    Good
  </h1>
</template>
```
