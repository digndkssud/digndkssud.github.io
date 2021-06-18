# import { ref } from 'vue'

```vue
<template>
  <div @click="increase">
    {{ count }}
  </div>
</template>

<script>
//반응성을 위해 { ref }를 사용해준다.
import { ref } from 'vue'

export default {
  setup (){
    let count = ref(0)
    function increase(){
      count.value += 1
    }

    return {
      count,
      increase
    }
  }
}
</script>
```