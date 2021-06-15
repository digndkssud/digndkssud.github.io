# 폼 입력 바인딩 - v-model
## v-model은 한글을 다 입력해야함
## 따라서 한글 사용할 때는 단방향 바인딩을 해줄 필요성 있음.

```vue
<template>
  <h1>{% raw %}{{ msg1 }}{% endraw %}</h1>
  <input
    type="text"
    :value="msg1"
    @input="msg1 = $event.target.value" />

    
  <!-- v-model의 경우 한글 지원이 한 박자 느리다 -->
  <h1>{% raw %}{{ msg2 }}{% endraw %}</h1>
  <input
    type="text"
    v-model="msg2 " />
  <h1>{{ checked }}</h1>
  <input
    type="checkbox"
    v-model="checked" />
</template>

<script>
export default {
  data(){
    return {
      msg1: '한글 단반향',
      msg2: '영어 v-model',
      checked: false
    }
  }
}
</script>
```

