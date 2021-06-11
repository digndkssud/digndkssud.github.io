# class와 스타일 바인딩

---

# class

```vue
<template>
  <!-- isActive가 ture면 active 추가-->
  <h1 
    :class="{ active: isActive }"
    @click="activate">
    Hello?!({{ isActive }})
  </h1>
</template>

<script>
export default {
  data(){
    return {
      isActive: false
    }
  },
  methods: {
    activate(){
      this.isActive = true
    } 
  }
}
</script>

<style scoped>
  .active{
    color: red;
    font-weight: bold;
  }
  
</style>
```


# 스타일 바인딩

```vue

<template>
  <h1>
    :style="[fontStyle, backgroundStyle]"
    @click="changeStyle">
    Hello?!
  </h1>
</template>

<script>
export default {
  data(){
    return {
      fontStyle: {
        color: 'orange',
        fontsize: '30px'
      },
      backgroundStyle: {
        backgroundColor: 'black'
      }
    }
  },
  methods: {
    changeStyle(){
      this.fontStyle.color = 'red'
      this.fontStyle.fontSize = '50px'
    }
  }
}
</script>
```