<template>
  <div class="HelloWorld">
    <h1>{{ msg }}</h1>
    <!--<h3 v-on:click="dosomething">{{ my_message }}</h3>-->
    <button v-on:click="dosomething">{{ my_message }}</button>
    <h2>Essential Links</h2>
  </div>
</template>

<script>
  export default {
    name: 'Hello',
    data () {
      return {
        msg: 'Welcome to Your Vue.js App',
        my_message: '点击事件'
      }
    },
    methods: {
      dosomething: function () {
      }
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
