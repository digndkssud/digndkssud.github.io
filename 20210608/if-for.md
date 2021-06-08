# 선언적 렌더링과 입력 핸들링
```vue

<template>
// h1을 클릭하면 increase라는 핸들러를 동작시킨다.
  <h1 @click="increase"> 
    {{ count }}
  </h1>
</template>


<script>
export default {
  data(){
    return {
      count: 0
    }
  },
  methods:{
    increase(){
      this.count += 1
    }
  }
}
</script>


<style>
 h1{
   font-size: 50px;
   color: royalblue;
 }
</style>
```

# 조건문과 반복문


```vue
<template>
  <h1 @click="increase">
    {{ count }}
  </h1>
  // 'v-'으로 시작하는 것들을 디렉티브(Directive)
  // if문
  <div v-if="count > 4"> 
    4보다 큽니다!
  </div>

  // for문
  <ul>
    <li
      v-for="fruit in fruits"
      :key="fruit">
      {{ fruit }}
    </li>
  </ul>
</template>

```
# components 사용법

```vue

App.vue에 사용하고자하는 components에 소속되어있는 vue를 import 시켜준다

<template>
  <ul>
    <hello
        v-for="fruit in fruits"
        :key="fruit"
        :name="fruit">
        {{ fruit }}
    </hello>
  </ul>
</template>

<script>
import Fruit from '~/components/Fruit'

export default {
  components:{
    hello: Fruit
  }

</script>


// scoped는 해당 vue에만 영향이 끼치게 제어해줌.
<style scoped lang="scss">
  h1 {
    color: red !important;
  }
</style>


```