# provide / inject

```plaintext
App.vue에 있는 data message를 Child.vue에서 출력하기 위해
App.vue => Parent.vue => Child.vue 이어주기 위하여 props를 사용해 한 단계 씩 내려주고 있다.
----------------------------------
조상 컴포넌트에서 후손 컴포넌트로 값을 넘겨주기 위해서는
매개 컴포넌트가 필요하다.
그것을 위해 provide와 inject를 사용
다만 반응성이 없어지기 때문에 
computed를 사용하여 콜백을 이용해줘야한다.
```

# App.veu
```vue
<template>
  <button @click="message = 'Good?'">
    Click
  </button>
  <h1>App: {{ message }}</h1>
  <Parent />
</template>

<script>
import Parent from '~/components/Parent'
import { computed } from 'vue' 

export default {
  components: {
    Parent
  },
  data(){
    return {
      message: 'Hello world!'
    }
  },
  provide() {
    return {
      msg: computed(() =>  this.message)
    }
  }
}
</script>
```

# Parent.vue
```vue
<template>
  <Child />
</template>

<script>
import Child from '~/components/Child'

export default {
  components: {
    Child
  }
}
</script>
```

# Child.vue
```vue
<template>
  <div>
    Child: {{ msg.value }}
  </div>
</template>

<script>
export default {
  inject: ['msg']
}
</script>
```