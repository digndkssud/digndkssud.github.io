# 이벤트 핸들링 - 이벤트 수식어

---

# @click.prevent.once
## prevent => html의 기본 값 이벤트를 실행 X.
## once => 해당 메소드를 한 번만 동작시킴.

```vue
<template>
  <a
    href="https://naver.com"
    target="_blank"
    @click.prevent.once="handler">
    NAVER
  </a>
</template>

<script>
export default {
  methods: {
    handler() {
      console.log('ABC!')
    }
  }
}
</script>
```

---
# 이벤트 버블링
## 자식 요소에서 부모 요소까지 전파
## 그것을 막기 위하여  @click.stop을 사용한다.
##  @click.stop= ""


```vue
<template>
  <div
    class="parent"
    @click="handlerA">
    <div
      class="child"
      @click.stop="handlerB"></div>
  </div>
</template>

<script>
export default {
  methods: {
    handlerA(){
      console.log('A')
    },
    handlerB(){
      console.log('B')
    }
  }
}
</script>

<style scoped lang="scss">
  .parent{
    width: 200px;
    height: 100px;
    background-color: royalblue;
    margin: 10px;
    padding: 10px;
    .child{
      width:100px;
      height: 100px;
      background-color: orange;
    }
  }
</style>
```
---
# 이벤트 캡쳐링
## 부모 요소를 먼저 읽어낸다 

```vue
<template>
  <div
    class="parent"
    @click.capture.stop="handlerA">
    <div
      class="child"
      @click="handlerB"></div>
  </div>
</template>

```
---

# 자기 자신만 선택하기

```vue
<template>
  <div
    class="parent"
    @click.self="handlerA">
    <div
      class="child"></div>
  </div>
</template>

```
# wheel & passive 
## wheel => 마우스 휠 동작 시킬 때마다 메소드를 동작시킴
## passive => 화면과 로직을 따로 나누어서 동작시킴. 최대 5배 속도 차이.
```vue
<template>
  <div
    class="parent"
    @wheel.passive="handler">
    <div
      class="child"></div>
  </div>
</template>

<script>
export default {
  methods: {
    handler(event){
      for(let i =0; i< 10000; i += 1){
        console.log(event)
      }
    }
  }
}
</script>

<style scoped lang="scss">
  .parent{
    width: 200px;
    height: 100px;
    background-color: royalblue;
    margin: 10px;
    padding: 10px;
    overflow: auto;
    .child{
      width:100px;
      height: 2000px;
      background-color: orange;
    }
  }
</style>
```