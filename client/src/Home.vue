<template>
    <img alt="Vue logo" src="./assets/logo.png">
    <div>
        <HelloWorld msg="Hello"/>
    </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
export default {
  name: 'home-page',
  components: {
    HelloWorld
  },
  props: {
    msg: String
  }
}
</script>