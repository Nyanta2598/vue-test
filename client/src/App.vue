<template>
  <h1>{{ msg }}</h1>
  <div>
    <img alt="Vue logo" src="./assets/logo.png">
    <p>Types of Vue Project</p>
    <div>
      <AddOptionsList />
    </div>
    <div>
      <AddCompositionList />
    </div>
  </div>
</template>
<script>

import AddOptionsList from './components/AddOptionsList.vue'
import AddCompositionList from './components/AddCompositionList.vue'

export default {
  name: 'App',
  components: {
     AddOptionsList,AddCompositionList
  },
  props: {
    msg: String
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
