### 父子组件通过prop异步传递数据的时候，通过watch解决子组件created钩子函数中读取不到prop值
``````vue
// 父组件中
<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld :msg="msg"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      msg: 'Welcome to your Vue.js app'
    }
  },
  created() {
    let app = this;
    setTimeout(()=>{
      app.msg = 'this is new value'
    })
  }
}
</script>
``````
```vue
// 子组件中
<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  created() {
    console.log(this.msg);
    this.initData()
  },
  mounted() {
    console.log(this.msg);
  },
  watch: {
    msg: function(val) {
      this.msg = val
    }
  }
}
</script>

```