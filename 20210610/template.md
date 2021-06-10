# 보간법(Interpolation)
# v-once
## 데이터가 변경되어도 갱신되지 않음

```vue
<template>
  <h1
    v-once
    @click="add">
    {% raw %}
    {{ msg }}
    {% endraw %}
  </h1>
</template>

<script>
export default {
  data(){
    return {
      msg: 'Hello world!'
    }
  },
  methods:{
    add(){
      this.msg += '!'
    }
  }
}
</script>

```
---

# 원시 HTML

# v-html
```vue
<template>
  <h1>
    {% raw %}
    {{ msg }}
    {% endraw %}
  </h1>
  <h1 v-html="msg"></h1>
</template>

<script>
export default {
  data(){
    return {
      msg: '<div style="color: red;">Hello!!</div>'
    }
  }
}
</script>

```
---

# v-bind

```vue
<template>
  <!-- 전체문법 --> 
  <h1 v-bind:class="msg">
  <!-- 약어 --> 
  <h1 :class="msg">
  <!-- 더 간단하게 -->
  <h1 
    :[attr]="'active'"
    @[event]="add">
    {% raw %}
    {{ msg }}
    {% endraw %}
  </h1>
</template>

<script>
export default {
  data(){
    return {
      msg: 'active',
      attr: 'class',
      event: 'click'
    }
  },
  methods:{
    add(){
      this.msg += '!'
    }
  }
}
</script>
<style scoped>
  .active{
    color: royalblue;
    font-size: 100px;
  }
</style>


```
