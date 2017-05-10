<template>
<div class="hello">
  <header-bar text-align='left'></header-bar>
  <home-bar></home-bar>
</div>
  
</template>

<script>
import HeaderBar from "@/components/base/header"
import homeBar from "@/components/page/home"
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components:{
    HeaderBar,
    homeBar
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
