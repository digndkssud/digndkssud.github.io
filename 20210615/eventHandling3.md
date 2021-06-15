# 키 수식어
## @keydown.ctrl.shift.a 와 같이 체이닝으로 사용 가능하다.

```vue
<template>
  <input
    type="text"
    @keydown.ctrl.shift.a="handler" />
</template>

<script>
export default {
  methods: {
    handler () {
      console.log('Enter!!')
    }
  }
}
</script>
```