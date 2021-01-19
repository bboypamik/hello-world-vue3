<template>
  <h1>Hello-World</h1>
  <p>My name is {{myName}} and my dog name is {{myDog}}</p>
</template>

<script>

export default {

  data(){
    return {
    myName: 'Miro',
    myDog: 'Mrvica'
    }
  },

  mounted(){
    console.log(this.myName)
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
