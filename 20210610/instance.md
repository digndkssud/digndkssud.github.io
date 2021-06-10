# 인스턴스와 라이프사이클

```vue
<template>
  <h1>{{ count }}</h1>
</template>

<script>
export default {
  data(){
    return {
      count: 2
    }
  },

  // App이 생성되기 전
  beforeCreate(){
    console.log('Before Create!',this.count) // undefined 출력
  },
  // App이 생성된 후
  created(){
    console.log('Created!',this.count) // count : 2 값 출력
  },

  //html을 연결하기 전
  beforeMount(){
    console.log('beforeMount!')
    console.log(document.querySelector('h1')) // null 값 출력
  },
  //html을 연결한 후
  mounted(){
    console.log('Mounted!')
    console.log(document.querySelector('h1')) // <h1>2</h1> 출력
  } 
}
</script>
```