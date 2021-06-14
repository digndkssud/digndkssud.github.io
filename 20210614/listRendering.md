# list 렌더링

```vue
$ npm i -D shortid
고유한 아이디를 생성해준다.

<template>
  <button @click="handler">
    Click me!
  </button>
  <ul>
    <li
      v-for="{ id,name } in newFruits"
      :key="id">
      ({% raw %}{{ name }}-{{ id }}{% endraw %})
    </li>
  </ul>
</template>

<script>
import shortid from 'shortid'
export default {
  data() {
    return {
      fruits: ['Apple','Banana','Cherry'],
      // newFruits:[
      //   {id:0, name: 'Apple'},
      //   {id:1, name: 'Banana'},
      //   {id:2, name: 'Cherry'}
      // ]
    } 
  },
  computed:{
    newFruits() {
      return this.fruits.map(fruit => ({
        id: shortid.generate(),
        name: fruit
      })) 
    }
  },
  methods: {
    handler(){
      this.fruits.push('Orange')
    }
  }
}
</script>

```
